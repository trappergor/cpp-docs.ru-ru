---
title: "Использование объектов accelerator и accelerator_view | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 18f0dc66-8236-4420-9f46-1a14f2c3fba1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8cc676407a88979679a362b3d36f361614524432
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="using-accelerator-and-acceleratorview-objects"></a>Использование объектов accelerator и accelerator_view
Можно использовать [accelerator](../../parallel/amp/reference/accelerator-class.md) и [accelerator_view](../../parallel/amp/reference/accelerator-view-class.md) классах, чтобы задать устройство или эмулятор для выполнения коде C++ AMP. Системы могут иметь несколько устройств или эмуляторов, которые отличаются по объему памяти, поддержки общей памяти, поддержка отладки или поддержки двойной точности. C++ Accelerated Massive Parallelism (C++ AMP) предоставляет интерфейсы API, которые можно использовать для проверки доступных сочетания клавиш, задан профиль по умолчанию, укажите нескольких объектах accelerator_view для нескольких вызовов parallel_for_each и выполнять специальные задачи отладки.  
  
## <a name="using-the-default-accelerator"></a>С помощью сочетания клавиш по умолчанию  
 Среда выполнения C++ AMP выбирает клавишей быстрого доступа по умолчанию, если написать код, чтобы выбрать одну из них. Среда выполнения выбирает сочетания клавиш по умолчанию следующим образом:  
  
1.  Если приложение выполняется в режиме отладки, клавишей быстрого доступа, который поддерживает отладку.  
  
2.  В противном случае сочетания клавиш, указанные в переменной среды CPPAMP_DEFAULT_ACCELERATOR в том случае, если оно задано.  
  
3.  В противном случае неэмулированных устройства.  
  
4.  В противном случае устройство, которое имеет наибольшее количество доступной памяти.  
  
5.  В противном случае устройства, который не присоединен к отображаемому.  
  
 Кроме того, среда выполнения определяет `access_type` из `access_type_auto` для сочетания клавиш по умолчанию. Это означает, что сочетания клавиш по умолчанию использует общей памяти, если он поддерживается, и если известно, что его характеристики производительности (полосы пропускания и задержки) совпадать с выделенной памяти (без общего доступа).  
  
 Свойства сочетаний клавиш по умолчанию можно определить путем создания сочетания клавиш по умолчанию и проверка его свойств. В следующем примере кода печатается путь, объем памяти сочетаний клавиш, поддержки общей памяти, поддержку двойной точности и ограниченную поддержку двойной точности, сочетания клавиш по умолчанию.  
  
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
 Можно задать переменную среды CPPAMP_DEFAULT_ACCELERATOR, чтобы задать `accelerator::device_path` сочетания клавиш по умолчанию. Путь зависит от оборудования. В следующем коде используется `accelerator::get_all` функцию, чтобы получить список доступных клавиш, а затем отображает путь и характеристики каждый сочетаний клавиш.  
  
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
 Чтобы выбрать клавишей быстрого доступа, используйте `accelerator::get_all` метод, чтобы получить список доступных клавиш, а затем выберите одну на основе его свойств. В этом примере показано, как выбрать сочетаний клавиш, который имеет наибольший объем памяти:  
  
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
>  Одно из сочетания клавиш, которые возвращаются по `accelerator::get_all` — сочетание клавиш ЦП. Не удается выполнить код ЦП сочетания клавиш. Чтобы отфильтровать ЦП сочетания клавиш, сравните значение [device_path](reference/accelerator-class.md#device_path) свойство ускоритель, возвращенный `accelerator::get_all` со значением [accelerator::cpu_accelerator](reference/accelerator-class.md#cpu_accelerator). Дополнительные сведения см. в разделе «Специальные сочетания клавиш» в этой статье.  
  
## <a name="shared-memory"></a>Общая память  
 Общая память — это память, может осуществляться ЦП и сочетания клавиш. Использование общей памяти устраняет и значительно сокращает затраты на копирование данных между центральным Процессором и сочетания клавиш. Несмотря на то, что общий объем памяти, он не может получать одновременно ЦП и сочетания клавиш и благодаря этому неопределенное поведение. Свойства сочетаний клавиш [supports_cpu_shared_memory](reference/accelerator-class.md#supports_cpu_shared_memory) возвращает `true` если сочетания клавиш поддерживает общей памяти и [default_cpu_access_type](reference/accelerator-class.md#default_cpu_access_type) свойство получает значение по умолчанию [access_type](reference/concurrency-namespace-enums-amp.md#access_type) для памяти, выделенной в `accelerator`— например, `array`, связанные с `accelerator`, или `array_view` объектов, взаимодействующих с `accelerator`. 
  
 Среда выполнения C++ AMP автоматически выбирает лучший по умолчанию `access_type` для каждого `accelerator`, но характеристики производительности общей памяти (полосы пропускания и задержки) может быть хуже, чем те, памяти, выделенной сочетаний клавиш (без общего доступа), при чтении с ЦП, запись из ЦП или оба. Если общей памяти выполняет, а также выделенной памяти для чтения и записи с ЦП, среда выполнения по умолчанию `access_type_read_write`; в противном случае среда выполнения выбирает меньшем по умолчанию `access_type`и позволяет приложению переопределить его, если доступ к памяти шаблоны его вычисление ядер выиграть от другой `access_type`.  
  
 В следующем примере кода показано, как определить, является ли сочетания клавиш по умолчанию поддерживает общей памяти и затем переопределяет его типом доступа по умолчанию создает `accelerator_view` из него.  
  
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
  
 `accelerator_view` Всегда отражает `default_cpu_access_type` из `accelerator` он связан, и предоставляет интерфейс, не переопределить или изменить его `access_type`.  
  
## <a name="changing-the-default-accelerator"></a>Изменение сочетаний клавиш по умолчанию  
 Сочетания клавиш по умолчанию можно изменить с помощью `accelerator::set_default` метод. Сочетания клавиш по умолчанию можно изменить только в том случае, если на каждое приложение выполнения и вам необходимо изменить его перед выполнением любого кода в GPU. Возвращать все последующих вызовов функций для изменения сочетаний клавиш `false`. Если вы хотите использовать различные сочетания в вызове `parallel_for_each`, ознакомьтесь с разделом «С помощью нескольких акселераторы» в этой статье. В следующем примере кода задает сочетания клавиш по умолчанию на адрес, который не эмулируется, не подключен к отображения и поддерживает двойной точности.  
  
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
 Существует два способа использования нескольких сочетания клавиш в приложении:  

-   Можно передать `accelerator_view` объектов с вызовами [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) метод.  
  
-   Можно создать `array` с помощью конкретного `accelerator_view` объекта. Среда выполнения C + AMP получат `accelerator_view` объекта из записанные `array` объекта в лямбда-выражения.  
  
## <a name="special-accelerators"></a>Специальные сочетания клавиш  
 Пути устройства три специальные сочетания клавиш доступны как свойства `accelerator` класса:  
  
- [Элемент данных Accelerator::direct3d_ref](reference/accelerator-class.md#direct3d_ref): данный акселератор однопоточных использует программное обеспечение на ЦП, чтобы эмулировать универсального видеокарты. Он используется по умолчанию для отладки, но полезно не в производственной среде, так как он работает медленнее, чем акселераторы оборудования. Кроме того она доступна только в пакет SDK DirectX и пакета Windows SDK и маловероятно на компьютерах клиентов. Дополнительные сведения см. в разделе [отладка кода GPU](/visualstudio/debugger/debugging-gpu-code).  
  
- [Элемент данных Accelerator::direct3d_warp](reference/accelerator-class.md#direct3d_warp): это решение предоставляет резервной стратегии о выполнении кода C++ AMP на многоядерных процессорах, использующих Streaming SIMD расширения (SSE).  
  
- [элемент данных Accelerator::cpu_accelerator](reference/accelerator-class.md#cpu_accelerator): это решение можно использовать для настройки размещения массивы. Он не может выполнить код C++ AMP. Дополнительные сведения см. в разделе [массивы промежуточного хранения в C++ AMP](http://go.microsoft.com/fwlink/p/?linkId=248485) разместить на параллельное программирование в блоге машинного кода.  
  
## <a name="interoperability"></a>Взаимодействие  
 Среда выполнения C++ AMP поддерживает взаимодействие между `accelerator_view` класса и Direct3D [ID3D11Device интерфейс](http://go.microsoft.com/fwlink/p/?linkId=248488). [Create_accelerator_view](reference/concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view) принимает `IUnknown` интерфейс и возвращает `accelerator_view` объекта. [Get_device](http://msdn.microsoft.com/en-us/8194125e-8396-4d62-aa8a-65831dea8439) принимает `accelerator_view` объекта и возвращает `IUknown` интерфейса.  
  
## <a name="see-also"></a>См. также  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [Отладка кода GPU](/visualstudio/debugger/debugging-gpu-code)   
 [Класс accelerator_view](../../parallel/amp/reference/accelerator-view-class.md)
