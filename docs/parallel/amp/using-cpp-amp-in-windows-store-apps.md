---
title: Использование C++ AMP в приложениях UWP | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 85577298-2c28-4209-9470-eb21048615db
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5736c84f21535222de5659780968efd98e1467da
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33696159"
---
# <a name="using-c-amp-in-uwp-apps"></a>Использование C++ AMP в приложениях UWP
C++ AMP (C++ Accelerated Massive Parallelism) можно использовать в приложении универсальной платформы Windows (UWP) для выполнения вычислений на GPU (единица обработки графики) или других вычислений сочетания клавиш. Однако C++ AMP не предоставляет интерфейсы API для работы непосредственно с типами среды выполнения Windows, а в среде выполнения Windows нет программы-оболочки для C++ AMP. При использовании в коде типов среды выполнения Windows, включая созданные самостоятельно, необходимо преобразовать их в совместимые с С++ AMP типы.  
  
## <a name="performance-considerations"></a>Особенности производительности  
 Если вы используете [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] ([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]) для создания приложения универсальной платформы Windows (UWP), рекомендуется использовать типы данных обычного старого (POD) вместе с хранилищем смежных — например, `std::vector` или массивы в стиле языка C — для данных, который будет использоваться с помощью C++ AMP. Это поможет добиться более высокой производительности, чем с помощью типов, не являющимся POD или контейнеры Windows RT, так как без маршалирования не требуются.  
  
 В C++ AMP ядра, для доступа к данным, которые хранятся таким образом, достаточно поместить `std::vector` массива или массива хранения данных в `concurrency::array_view` и затем использовать представление массива в `concurrency::parallel_for_each` цикл:  
  
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
  
## <a name="marshaling-windows-runtime-types"></a>Маршалинг типов среды выполнения Windows  
 При работе с интерфейсами API среды выполнения Windows может быть нужно использовать C++ AMP с данными, которые хранятся в контейнере среды выполнения Windows, например`Platform::Array<T>^`, или в сложных типах данных, таких как классы и структуры, объявленные с помощью ключевого слова `ref` или `value`. В этих ситуациях необходимо выполнить некоторые дополнительные действия, чтобы сделать данные доступными в C++ AMP.  
  
### <a name="platformarrayt-where-t-is-a-pod-type"></a>Platform::Array\<T > ^, где T — тип POD  
 Если возникли `Platform::Array<T>^` и T — тип POD, доступ к его базовое хранилище с помощью `get` функции-члена:  
  
```cpp  
Platform::Array<float>^ arr; // Assume that this was returned by a Windows Runtime API  
concurrency::array_view<float, 1> av(arr->Length, &arr->get(0));
```  
  
 Если T не является типом POD, для использования с C++ AMP данных используйте метод описан в следующем разделе.  
  
### <a name="windows-runtime-types-ref-classes-and-value-classes"></a>Типы среды выполнения Windows: классы ссылки и классы значений  
 C++ AMP не поддерживает сложные типы данных. Сюда входят типы, не являющимся POD и любые типы, объявленные с помощью `ref` ключевое слово или `value` ключевое слово. Если используется неподдерживаемый тип `restrict(amp)` создается контекст, ошибка времени компиляции.  
  
 При возникновении неподдерживаемый тип, можно скопировать интересные части своих данных `concurrency::array` объекта. Помимо предоставления данных для C++ AMP для использования, этот подход вручную копирования также могут повысить производительность путем увеличения локальность данных, а также за счет того, что данные, которые не будут использоваться не копируется сочетания клавиш. Можно повысить производительность дополнительно с помощью *промежуточных массива*, это особая форма `concurrency::array` , предоставляет подсказку для выполнения AMP, массива должна быть оптимизировано для частых передачи между ним и другие массивы в сочетание клавиш.  
  
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
    property int b;  
};  
  
// Some other file  
  
std::vector<pixel_color^> pixels (256);
  
for (pixel_color ^pixel : pixels)   
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
        red_vec[i] = pixels[i]->r;  
        blue_vec[i] = pixels[i]->b;  
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
  
## <a name="see-also"></a>См. также  
 [Создание первого приложения UWP, с помощью C++](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)   
 [Создание компонентов среды выполнения Windows в C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)

