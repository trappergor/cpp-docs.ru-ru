---
title: Использование C++ AMP в приложениях универсальной платформы Windows
ms.date: 11/04/2016
ms.assetid: 85577298-2c28-4209-9470-eb21048615db
ms.openlocfilehash: 31fede0a2419e56d53cb16521b08067dac5facc6
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57272663"
---
# <a name="using-c-amp-in-uwp-apps"></a>Использование C++ AMP в приложениях универсальной платформы Windows

C++ AMP (C++ Accelerated Massive Parallelism) в приложении универсальной платформы Windows (UWP) можно использовать для выполнения вычислений на GPU (графическом процессоре) или другие вычислительные сочетаниях клавиш. Однако C++ AMP не предоставляет интерфейсы API для работы непосредственно с типами среды выполнения Windows, а в среде выполнения Windows нет программы-оболочки для C++ AMP. При использовании в коде типов среды выполнения Windows, включая созданные самостоятельно, необходимо преобразовать их в совместимые с С++ AMP типы.

## <a name="performance-considerations"></a>Особенности производительности

Если вы используете расширения компонентов Visual C++ C + +/ CX для создания приложения универсальной платформы Windows (UWP), рекомендуется использовать типы plain-old-data (POD) вместе со смежным хранилищем — например, `std::vector` или массивы в стиле C — для данных, который будет используется с с ++ AMP. Это может помочь добиться более высокой производительности, чем с помощью отличных от POD типов или контейнеров Windows RT, так как не маршалинга не требуются.

В ядре на C++ AMP, для доступа к данным, которые хранятся в этом случае достаточно поместить `std::vector` или хранилище массивов в `concurrency::array_view` , а затем использовать представление массива в `concurrency::parallel_for_each` цикла:

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

При работе с API среды выполнения Windows, может потребоваться использовать C++ AMP на данные, хранящиеся в контейнере среды выполнения Windows, такие как `Platform::Array<T>^` или в сложных типах данных, таких как классы или структуры, объявленные с помощью **ref** Ключевое слово или **значение** ключевое слово. В этих случаях необходимо выполнить некоторые дополнительные действия, чтобы сделать данные доступными в C++ AMP.

### <a name="platformarrayt-where-t-is-a-pod-type"></a>Platform::Array\<T > ^, где T — тип POD

При обнаружении `Platform::Array<T>^` и T — тип POD, можно получить доступ к его базовому хранилищу с помощью `get` функция-член:

```cpp
Platform::Array<float>^ arr; // Assume that this was returned by a Windows Runtime API
concurrency::array_view<float, 1> av(arr->Length, &arr->get(0));
```

Если T не является типом POD, используйте технику, описанную в следующем разделе, для использования данных с помощью C++ AMP.

### <a name="windows-runtime-types-ref-classes-and-value-classes"></a>Типы среды выполнения Windows: классы ссылки и классы значений

C++ AMP не поддерживает сложные типы данных. Сюда входят типы, отличные от POD и все типы, которые объявляются с помощью **ref** ключевое слово или **значение** ключевое слово. Если используется неподдерживаемый тип `restrict(amp)` создается контекст, ошибка времени компиляции.

При возникновении неподдерживаемый тип можно копировать части интересные его данных в `concurrency::array` объекта. Кроме того, что данные доступны для использования C++ AMP, этот подход копирования вручную также можно повысить производительность, повышая локальность данных и гарантируя, что данные, которые не будут использоваться не копироваться на ускоритель. Можно повысить производительность с помощью *массива промежуточного хранения*, который представляет собой специальную форму из `concurrency::array` которая содержит подсказку выполнение AMP, массив должен быть частой оптимизирован для передачи между и другими массивами на сочетание клавиш.

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

[Создание первого приложения универсальной платформы Windows на C++](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)<br/>
[Создание компонентов среды выполнения Windows в C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
