---
title: Использование объектов accelerator и accelerator_view
ms.date: 11/04/2016
ms.assetid: 18f0dc66-8236-4420-9f46-1a14f2c3fba1
ms.openlocfilehash: 05ca53d075867fefa43f7471bb795040d075274e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57272908"
---
# <a name="using-accelerator-and-acceleratorview-objects"></a>Использование объектов accelerator и accelerator_view

Можно использовать [accelerator](../../parallel/amp/reference/accelerator-class.md) и [accelerator_view](../../parallel/amp/reference/accelerator-view-class.md) классы для определения устройства или эмулятора для выполнения кода C++ AMP. Система может иметь несколько устройств или эмуляторов, которые отличаются объемом памяти, поддержкой общей памяти, поддержку отладки или поддержкой двойной точности. C++ Accelerated Massive Parallelism (C++ AMP) предоставляет API, которые можно использовать для проверки доступных ускорителей, задать один по умолчанию, укажите несколько представлений ускорителей для множественных вызовов parallel_for_each и выполнять специальные задачи отладки.

## <a name="using-the-default-accelerator"></a>Использование ускорителя по умолчанию

Среда выполнения C++ AMP выбирает ускоритель по умолчанию, если не писать код для выбора конкретного ускорителя. Среда выполнения выбирает ускоритель по умолчанию следующим образом:

1. Если приложение выполняется в режиме отладки, ускоритель, поддерживающий отладку.

2. В противном случае выбирается ускоритель, который указан в переменной среды CPPAMP_DEFAULT_ACCELERATOR, если он задан.

3. В противном случае — неэмулированное устройство.

4. В противном случае — устройство с наибольшим объемом доступной памяти.

5. В противном случае — устройство, которое не подсоединено к дисплею.

Кроме того, среда выполнения задает `access_type` из `access_type_auto` для ускорителя по умолчанию. Это означает, что сочетание клавиш по умолчанию использует общую память, если он поддерживается, и если известны характеристики производительности (пропускной способности и задержки), должен совпадать с выделенной (необщей) памяти.

Можно определить свойства ускорителя по умолчанию, создав ускорителя по умолчанию и просмотра его свойств. В следующем примере кода выводится путь, объем памяти сочетания клавиш, поддержки общей памяти, поддержку двойной точности и ограниченную поддержку двойной точности ускорителя по умолчанию.

```cpp
void default_properties() {
    accelerator default_acc;
    std::wcout << default_acc.device_path << "\n";
    std::wcout << default_acc.dedicated_memory << "\n";
    std::wcout << (accs[i].supports_cpu_shared_memory ?
        "CPU shared memory: true" : "CPU shared memory: false") << "\n";
    std::wcout << (accs[i].supports_double_precision ?
        "double precision: true" : "double precision: false") << "\n";
    std::wcout << (accs[i].supports_limited_double_precision ?
        "limited double precision: true" : "limited double precision: false") << "\n";
}
```

### <a name="cppampdefaultaccelerator-environment-variable"></a>Переменная среды CPPAMP_DEFAULT_ACCELERATOR

Можно задать переменную среды CPPAMP_DEFAULT_ACCELERATOR, чтобы указать `accelerator::device_path` ускорителя по умолчанию. Путь зависит от оборудования. В следующем коде используется `accelerator::get_all` функцию для получения списка доступных ускорителей, а затем отображает путь и характеристики каждого из них.

```cpp
void list_all_accelerators()
{
    std::vector<accelerator> accs = accelerator::get_all();

    for (int i = 0; i <accs.size(); i++) {
        std::wcout << accs[i].device_path << "\n";
        std::wcout << accs[i].dedicated_memory << "\n";
        std::wcout << (accs[i].supports_cpu_shared_memory ?
            "CPU shared memory: true" : "CPU shared memory: false") << "\n";
        std::wcout << (accs[i].supports_double_precision ?
            "double precision: true" : "double precision: false") << "\n";
        std::wcout << (accs[i].supports_limited_double_precision ?
            "limited double precision: true" : "limited double precision: false") << "\n";
    }
}
```

## <a name="selecting-an-accelerator"></a>Выбор ускорителя

Чтобы выбрать ускоритель, используйте `accelerator::get_all` метод для получения списка доступных ускорителей, а затем выберите одну на основе его свойств. В этом примере показано, как выбрать ускоритель с наибольшим памяти:

```cpp
void pick_with_most_memory()
{
    std::vector<accelerator> accs = accelerator::get_all();
    accelerator acc_chosen = accs[0];

    for (int i = 0; i <accs.size(); i++) {
        if (accs[i].dedicated_memory> acc_chosen.dedicated_memory) {
            acc_chosen = accs[i];
        }
    }

    std::wcout << "The accelerator with the most memory is "
        << acc_chosen.device_path << "\n"
        << acc_chosen.dedicated_memory << ".\n";
}
```

> [!NOTE]
> Один из ускорителей, возвращаемых `accelerator::get_all` — ЦП. Нельзя выполнять код на ускорителе ЦП. Чтобы отфильтровать ускоритель ЦП, сравните значение [device_path](reference/accelerator-class.md#device_path) ускорителя, возвращаемого `accelerator::get_all` со значением [accelerator::cpu_accelerator](reference/accelerator-class.md#cpu_accelerator). Дополнительные сведения см. в разделе «Специальные ускорители» в этой статье.

## <a name="shared-memory"></a>Общая память

Общая память — это память, может осуществляться и ЦП, так и сочетания клавиш. Использование общей памяти исключает или значительно снижает нагрузку копирования данных между ЦП и сочетаниями клавиш. Несмотря на то, что память используется совместно, не могут одновременно обращаться центральным Процессором и сочетания клавиш, и благодаря этому приведет к неопределенному поведению. Свойство [supports_cpu_shared_memory](reference/accelerator-class.md#supports_cpu_shared_memory) возвращает **true** Если сочетание клавиш поддерживает общей памяти и [default_cpu_access_type](reference/accelerator-class.md#default_cpu_access_type) свойство получает значение по умолчанию [access_type](reference/concurrency-namespace-enums-amp.md#access_type) для памяти, выделенной на `accelerator`— например, **массива**s, связанные с `accelerator`, или `array_view` объектов, доступных в `accelerator`.

Среда выполнения C++ AMP автоматически выбирает наилучшее по умолчанию `access_type` для каждого `accelerator`, но характеристики производительности (пропускной способности и задержки) общей памяти может быть хуже, чем accelerator выделенной (необщей) памяти, при чтении из ЦП, написание из ЦП, или оба. Если общая память работает, а также выделенная память для чтения и записи из ЦП, среда выполнения по умолчанию `access_type_read_write`; в противном случае среда выполнения выбирает более консервативный вариант `access_type`и позволяет приложению переопределить его, если доступ к памяти шаблоны его вычислительных ядер преимущества другой `access_type`.

В следующем примере кода показано, как определить, является ли ускоритель по умолчанию поддерживает общей памяти, а затем переопределяет тип доступа по умолчанию и создает `accelerator_view` от него.

```cpp
#include <amp.h>
#include <iostream>

using namespace Concurrency;

int main()
{
    accelerator acc = accelerator(accelerator::default_accelerator);

    // Early out if the default accelerator doesn’t support shared memory.
    if (!acc.supports_cpu_shared_memory)
    {
        std::cout << "The default accelerator does not support shared memory" << std::endl;
        return 1;
    }

    // Override the default CPU access type.
    acc.set_default_cpu_access_type(access_type_read_write);

    // Create an accelerator_view from the default accelerator. The
    // accelerator_view reflects the default_cpu_access_type of the
    // accelerator it’s associated with.
    accelerator_view acc_v = acc.default_view;
}
```

`accelerator_view` Всегда отражает `default_cpu_access_type` из `accelerator` он связан, и не предоставляет интерфейс для переопределения или изменения его `access_type`.

## <a name="changing-the-default-accelerator"></a>Изменение ускорителя по умолчанию

Сочетание клавиш по умолчанию можно изменить, вызвав `accelerator::set_default` метод. Сочетание клавиш по умолчанию можно изменить только в том случае, когда для каждого приложения выполнения и вам необходимо сменить его до выполнения любого кода на GPU. Все последующие вызовы функции для изменения ускорителя возвращают **false**. Если вы хотите использовать другой ускоритель при обращении к `parallel_for_each`, прочтите раздел «Использование нескольких ускорителей» в этой статье. В следующем примере кода задает сочетание клавиш по умолчанию, который не эмулируется, не подключен к дисплею и поддерживает двойной точности.

```cpp
bool pick_accelerator()
{
    std::vector<accelerator> accs = accelerator::get_all();
    accelerator chosen_one;

    auto result = std::find_if(accs.begin(), accs.end(),
        [] (const accelerator& acc) {
            return !acc.is_emulated &&
                acc.supports_double_precision &&
                !acc.has_display;
        });

    if (result != accs.end()) {
        chosen_one = *(result);
    }

    std::wcout <<chosen_one.description <<std::endl;
    bool success = accelerator::set_default(chosen_one.device_path);
    return success;
}
```

## <a name="using-multiple-accelerators"></a>Использование нескольких ускорителей

Существует два способа использования нескольких ускорителей в приложении:

- Вы можете передать `accelerator_view` объекты в вызовы [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) метод.

- Вы можете создать **массива** с помощью указанного `accelerator_view` объекта. Среда выполнения c++ AMP выберет `accelerator_view` объекта из перехваченного **массива** объекта в лямбда-выражения.

## <a name="special-accelerators"></a>Специальные ускорители

Пути трех специальных ускорителей доступны как свойства `accelerator` класса:

- [элемент данных Accelerator::direct3d_ref](reference/accelerator-class.md#direct3d_ref): Этот однопоточный ускоритель использует программное обеспечение на ЦП для эмуляции универсальной видеокарты. Он используется по умолчанию для отладки, но не имеет смысла в рабочей среде, так как он выполняется медленнее, чем аппаратные ускорители. Кроме того он доступен только в DirectX SDK и пакет SDK для Windows, и маловероятно, должны быть установлены на компьютерах клиентов. Дополнительные сведения см. в разделе [отладка кода GPU](/visualstudio/debugger/debugging-gpu-code).

- [элемент данных Accelerator::direct3d_warp](reference/accelerator-class.md#direct3d_warp): Этот ускоритель предоставляет резервное решение для выполнения кода C++ AMP на многоядерных процессорах, использующих Streaming SIMD Extensions (SSE).

- [элемент данных Accelerator::cpu_accelerator](reference/accelerator-class.md#cpu_accelerator): Это решение можно использовать для установки массивов промежуточного хранения. Он не может выполнять код C++ AMP. Дополнительные сведения см. в разделе [Staging Arrays in C++ AMP](https://blogs.msdn.microsoft.com/nativeconcurrency/2011/11/09/staging-arrays-in-c-amp/) блоге по параллельному программированию в блоге машинного кода.

## <a name="interoperability"></a>Взаимодействие

Среда выполнения C++ AMP поддерживает взаимодействие между `accelerator_view` класс и Direct3D [исходного интерфейса ID3D11Device](/windows/desktop/api/d3d11/nn-d3d11-id3d11device). [Create_accelerator_view](reference/concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view) альбома `IUnknown` и возвращающий `accelerator_view` объекта. [Get_device](reference/concurrency-direct3d-namespace-functions-amp.md#get_device) альбома `accelerator_view` объекта и возвращает `IUnknown` интерфейс.

## <a name="see-also"></a>См. также

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[Отладка кода GPU](/visualstudio/debugger/debugging-gpu-code)<br/>
[Класс accelerator_view](../../parallel/amp/reference/accelerator-view-class.md)
