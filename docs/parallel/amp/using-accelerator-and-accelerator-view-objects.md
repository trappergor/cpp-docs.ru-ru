---
title: Использование объектов accelerator и accelerator_view
ms.date: 11/04/2016
ms.assetid: 18f0dc66-8236-4420-9f46-1a14f2c3fba1
ms.openlocfilehash: 7807f0c1c572b2e7c3224cf0366233e2a28dbe07
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215898"
---
# <a name="using-accelerator-and-accelerator_view-objects"></a>Использование объектов accelerator и accelerator_view

Чтобы указать устройство или эмулятор для запуска C++ AMPного кода, можно использовать классы [ускорителя](../../parallel/amp/reference/accelerator-class.md) и [accelerator_view](../../parallel/amp/reference/accelerator-view-class.md) . Система может иметь несколько устройств или эмуляторов, которые отличаются объемом памяти, поддержкой общей памяти, поддержкой отладки или поддержкой двойной точности. C++ Accelerated Massive Parallelism (C++ AMP) предоставляет интерфейсы API, которые можно использовать для проверки доступных сочетаний клавиш, для одного из них по умолчанию укажите несколько accelerator_views для нескольких вызовов parallel_for_each и выполните специальные задачи отладки.

## <a name="using-the-default-accelerator"></a>Использование ускорителя по умолчанию

Среда выполнения C++ AMP выбирает ускоритель по умолчанию, если не написать код для выбора конкретного. Среда выполнения выбирает ускоритель по умолчанию следующим образом:

1. Если приложение работает в режиме отладки, ускоритель, поддерживающий отладку.

2. В противном случае — ускоритель, заданный переменной среды CPPAMP_DEFAULT_ACCELERATOR, если он установлен.

3. В противном случае — устройство без эмуляции.

4. В противном случае устройство с наибольшим объемом доступной памяти.

5. В противном случае — устройство, не подключенное к дисплею.

Кроме того, среда выполнения задает `access_type` `access_type_auto` для ускорителя по умолчанию. Это означает, что ускоритель по умолчанию использует общую память, если она поддерживается и если ее характеристики производительности (пропускная способность и задержка) совпадают с выделенной (не общей) памятью.

Чтобы определить свойства ускорителя по умолчанию, можно создать ускоритель по умолчанию и изучить его свойства. Следующий пример кода выводит на печать путь, объем памяти ускорителя, поддержку общей памяти, поддержку двойной точности и ограниченную поддержку двойной точности для ускорителя по умолчанию.

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

### <a name="cppamp_default_accelerator-environment-variable"></a>Переменная среды CPPAMP_DEFAULT_ACCELERATOR

Можно задать переменную среды CPPAMP_DEFAULT_ACCELERATOR, чтобы указать значение `accelerator::device_path` ускорителя по умолчанию. Путь зависит от оборудования. Следующий код использует `accelerator::get_all` функцию для получения списка доступных сочетаний клавиш, а затем отображает путь и характеристики каждого ускорителя.

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

## <a name="selecting-an-accelerator"></a>Выбор сочетания клавиш

Чтобы выбрать ускоритель, используйте `accelerator::get_all` метод для получения списка доступных сочетаний клавиш, а затем выберите один из его свойств. В этом примере показано, как выбрать ускоритель с наибольшим объемом памяти:

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
> Один из ускорителей, возвращаемых, `accelerator::get_all` — это УСКОРИТЕЛЬ ЦП. Невозможно выполнить код в ускорителе ЦП. Чтобы отфильтровать ускоритель ЦП, Сравните значение свойства [device_path](reference/accelerator-class.md#device_path) ускорителя, возвращаемое, `accelerator::get_all` со значением [ускорителя:: cpu_accelerator](reference/accelerator-class.md#cpu_accelerator). Дополнительные сведения см. в разделе "специальные ускорители" этой статьи.

## <a name="shared-memory"></a>Общая память

Общая память — это память, доступ к которой может осуществляться как ЦП, так и ускорителем. Использование общей памяти устраняет или значительно сокращает затраты на копирование данных между ЦП и ускорителем. Несмотря на то, что память является общей, она недоступна одновременно с ЦП и ускорителем, и это приводит к неопределенному поведению. Свойство ускорителя [supports_cpu_shared_memory](reference/accelerator-class.md#supports_cpu_shared_memory) возвращает значение **`true`** , если ускоритель поддерживает общую память, а свойство [default_cpu_access_type](reference/accelerator-class.md#default_cpu_access_type) получает [access_type](reference/concurrency-namespace-enums-amp.md#access_type) по умолчанию для памяти, выделенной для, например `accelerator` **массивы**, связанные с `accelerator` объектами, или `array_view` к которым осуществляется доступ в `accelerator` .

Среда выполнения C++ AMP автоматически выбирает оптимальное значение по умолчанию `access_type` для каждого `accelerator` , но характеристики производительности (пропускная способность и задержка) общей памяти могут быть хуже, чем в выделенной (необщей) памяти ускорителя при чтении из ЦП, записи из ЦП или в обоих случаях. Если общая память работает так же, как и выделенная память для чтения и записи из ЦП, среда выполнения по умолчанию принимает значение `access_type_read_write` ; в противном случае среда выполнения выбирает более консервативное значение по умолчанию `access_type` и позволяет приложению переопределить его, если шаблоны доступа к памяти для вычислительных ядер имеют другое преимущество `access_type` .

В следующем примере кода показано, как определить, поддерживает ли ускоритель по умолчанию общую память, а затем переопределить тип доступа по умолчанию и создать `accelerator_view` из него.

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

`accelerator_view`Всегда отражает объект, `default_cpu_access_type` `accelerator` с которым связан объект, и не предоставляет интерфейс для переопределения или изменения `access_type` .

## <a name="changing-the-default-accelerator"></a>Изменение ускорителя по умолчанию

Можно изменить ускоритель по умолчанию, вызвав `accelerator::set_default` метод. Вы можете изменить ускоритель по умолчанию только один раз для каждого выполнения приложения. его необходимо изменить перед выполнением кода на GPU. Все последующие вызовы функций для изменения сочетания клавиш **`false`** . Если вы хотите использовать другой ускоритель в вызове `parallel_for_each` , ознакомьтесь с разделом "использование нескольких ускорителей" этой статьи. В следующем примере кода в качестве ускорителя по умолчанию устанавливается один, который не эмулируется, не подключается к дисплею и поддерживает двойную точность.

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

- Объекты можно передавать в `accelerator_view` вызовы метода [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) .

- Объект **Array** можно создать с помощью определенного `accelerator_view` объекта. Среда выполнения C + AMP берет `accelerator_view` объект из захваченного объекта **массива** в лямбда-выражении.

## <a name="special-accelerators"></a>Специальные ускорители

В качестве свойств класса доступны пути к устройствам трех специальных ускорителей `accelerator` :

- [ускоритель::d Irect3d_ref элемент данных](reference/accelerator-class.md#direct3d_ref). Этот однопотоковый ускоритель использует программное обеспечение ЦП для эмуляции универсальной графической карты. Он используется по умолчанию для отладки, но он не полезен в рабочей среде, так как он медленнее, чем ускорители оборудования. Кроме того, он доступен только в пакете SDK DirectX и Windows SDK, и вряд ли будет установлен на компьютерах клиентов. Дополнительные сведения см. в разделе [Отладка кода GPU](/visualstudio/debugger/debugging-gpu-code).

- [ускоритель::d Irect3d_warp элемент данных](reference/accelerator-class.md#direct3d_warp). этот ускоритель предоставляет резервное решение для исполнения C++ amp кода на многоядерных ЦП, использующих расширения Streaming SIMD (SSE).

- [ускоритель:: Cpu_accelerator Data Member](reference/accelerator-class.md#cpu_accelerator). этот ускоритель можно использовать для настройки промежуточных массивов. Он не может выполнить C++ AMP код. Дополнительные сведения см. в разделе [промежуточные массивы в C++ amp](/archive/blogs/nativeconcurrency/staging-arrays-in-c-amp) POST по параллельному программированию в блоге машинного кода.

## <a name="interoperability"></a>Совместимость

Среда выполнения C++ AMP поддерживает взаимодействие между `accelerator_view` классом и [интерфейсом Direct3D ID3D11Device](/windows/win32/api/d3d11/nn-d3d11-id3d11device). Метод [create_accelerator_view](reference/concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view) принимает `IUnknown` интерфейс и возвращает `accelerator_view` объект. Метод [get_device](reference/concurrency-direct3d-namespace-functions-amp.md#get_device) принимает `accelerator_view` объект и возвращает `IUnknown` интерфейс.

## <a name="see-also"></a>См. также раздел

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[Отладка кода GPU](/visualstudio/debugger/debugging-gpu-code)<br/>
[Класс accelerator_view](../../parallel/amp/reference/accelerator-view-class.md)
