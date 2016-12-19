---
title: "Использование C++ AMP в приложениях для Магазина Windows | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 85577298-2c28-4209-9470-eb21048615db
caps.latest.revision: 14
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Использование C++ AMP в приложениях для Магазина Windows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Можно использовать C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\) в приложении [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] для выполнения вычислений на GPU \(графическом процессоре\) или другие средства ускорения вычислений.  Однако C\+\+ AMP не предоставляет API для работы непосредственно с типами среды выполнения Windows \(Windows Runtime\) и среда выполнения Windows не содержит программу\-оболочку для C\+\+ AMP.  При использовании типов среды выполнения Windows в коде, включая только что созданные самостоятельно, необходимо преобразовать их в совместимые с С\+\+ AMP типы.  
  
## Особенности производительности  
 При использовании [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] \([!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)]\) для создания приложения [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)], рекомендуется использовать типы данных \(POD\) вместе со смежным хранилищем, например `std::vector` или массивы в стиле С для данных, которые будут использоваться вместе с С\+\+ AMP.  Это может помочь достичь более высокой производительности, чем при использовании отличных от POD типов или контейнеров Windows RT, поскольку в этом случае не требуется маршализация.  
  
 В ядре на C\+\+ AMP, для доступа к данным, хранящимся таким образом, достаточно просто создать экземпляр `std::vector` или хранилище массивов в `concurrency::array_view`, а затем использовать представление массива в цикле `concurrency::parallel_for_each`.  
  
```cpp  
// simple vector addition example  
std::vector<int> data0(1024, 1);  
std::vector<int> data1(1024, 2);  
std::vector<int> data_out(data0.size(), 0);  
  
concurrency::array_view<int, 1> av0(data0.size(), data0);  
concurrency::array_view<int, 1> av1(data1.size(), data1);  
concurrency::array_view<int, 1> av2(data_out.size(), data2);   
  
av2.discard_data();  
  
concurrency::parallel_for_each(av0.extent, [=](concurrency::index<1> idx) restrict(amp)  
{  
  av2[idx] = av0[idx] + av1[idx];  
});  
  
```  
  
## Маршалинг типов среды выполнения Windows  
 При работе с API среды выполнения Windows может возникнуть необходимость использования C\+\+ AMP применительно к данным, которые хранятся в контейнере среды выполнения Windows, таком как `Platform::Array<T>^`, или в сложных типах данных, таких как классы и структуры, объявленные с помощью ключевого слова `ref` или ключевого слова `value`.  В этих случаях необходимо выполнить некоторую дополнительную работу, чтобы сделать данные доступными в C\+\+ AMP.  
  
### Platform::Array\<T\>^, где T — тип POD  
 При обнаружении `Platform::Array<T>^`, если T — тип POD, получить доступ к его базовому хранилищу можно просто с помощью функции\-члена `get`:  
  
```cpp  
Platform::Array<float>^ arr; // Assume that this was returned by a Windows Runtime API  
concurrency::array_view<float, 1> av(arr->Length, &arr->get(0));  
  
```  
  
 Если T — не тип POD, используйте технику, описанную в следующем разделе, для использования данных с С\+\+ AMP.  
  
### Типы среды выполнения Windows: классы ссылки и классы значений  
 C\+\+ AMP не поддерживает сложные типы данных.  Это включает типы, отличные от POD, и все типы, объявленные с помощью ключевого слова `ref` или ключевое слово `value`.  Если неподдерживаемый тип используется в контексте `restrict(amp)`, возникает ошибка времени компиляции.  
  
 Если будет встречаться неподдерживаемый тип можно копировать части интересные его данных в объект `concurrency::array`.  Помимо того, что эти данные доступны для использования C\+\+ AMP, подобный подход копирования вручную также повышает производительность, повышая локальность данных и гарантируя, что данные, которые не будут использоваться, не будут копироваться на ускоритель.  Можно повысить производительность с помощью *массива промежуточного хранения*, специальная форма `concurrency::array`, которая содержит подсказку выполнение AMP, что массив должен быть частой оптимизирован для передачи между сервером и другими массивами на заданном сочетании клавиш.  
  
```cpp  
// pixel_color.h  
ref class pixel_color sealed  
{  
 public:   
  pixel_color(Platform::String^ color_name, int red, int green, int blue)   
  {  
    name = color_name;  
    r = red;  
    g = green;  
    b = blue;  
  }  
  
  property Platform::String^ name;   
  property int r;  
  property int g;  
..property int b;  
};  
  
// Some other file  
std::vector<pixel_color^> pixels (256);   
  
for(pixel_color ^pixel : pixels)   
{  
  pixels.push_back(ref new pixel_color("blue", 0, 0, 255));  
}  
// Create the accelerators  
auto cpuAccelerator = concurrency::accelerator(concurrency::accelerator::cpu_accelerator);  
auto devAccelerator = concurrency::accelerator(concurrency::accelerator::default_accelerator);  
  
// Create the staging arrays  
concurrency::array<float, 1> red_vec(256, cpuAccelerator.default_view, devAccelerator.default_view);  
concurrency::array<float, 1>  blue_vec(256, cpuAccelerator.default_view, devAccelerator.default_view);   
  
// Extract data from the complex array of structs into staging arrays.  
concurrency::parallel_for(0, 256, [&](int i)  
{   
  red_vec[i] = pixels[i]->r; blue_vec[i] = pixels[i]->b;  
});  
  
// Array views are still used to copy data to the accelerator  
concurrency::array_view<float, 1> av_red(red_vec);  
concurrency::array_view<float, 1> av_blue(blue_vec);  
  
// Change all pixels from blue to red.  
concurrency::parallel_for_each(av_red.extent, [=](index<1> idx) restrict(amp)  
{  
  av_red[idx] = 255;  
  av_blue[idx] = 0;  
});  
  
```  
  
## См. также  
 [Создание первого приложения для Магазина Windows с использованием C\+\+](http://go.microsoft.com/fwlink/p/?LinkId=249073)   
 [Создание компонентов среды выполнения Windows в C\+\+](http://go.microsoft.com/fwlink/p/?LinkId=249076)