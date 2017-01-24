---
title: "Использование объектов accelerator и accelerator_view | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 18f0dc66-8236-4420-9f46-1a14f2c3fba1
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Использование объектов accelerator и accelerator_view
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Можно использовать [accelerator](../../parallel/amp/reference/accelerator-class.md) и [accelerator_view](../Topic/accelerator_view%20Class.md) классы для указания на устройстве или эмуляторе для запуска на коде C++ AMP. Системы может иметь несколько устройств или эмуляторов, которые отличаются от объема памяти, поддержки общей памяти, поддержку отладки и поддержки двойной точности. C++ Accelerated Massive Parallelism (C++ AMP) предоставляет интерфейсы API, которые можно использовать для проверки доступных ускорители, задать значение по умолчанию, укажите нескольких объектах accelerator_view для нескольких вызовов parallel_for_each и выполнять специальные задачи отладки.  
  
## <a name="using-the-default-accelerator"></a>С помощью сочетания клавиш по умолчанию  
 Среда выполнения C++ AMP выбирает ускоритель по умолчанию, если написать код, чтобы выбрать одну из них. Среда выполнения выбирает сочетания клавиш по умолчанию следующим образом:  
  
1.  Если приложение выполняется в режиме отладки, ускоритель, который поддерживает отладку.  
  
2.  В противном случае — сочетания клавиш, указанные в переменной среды CPPAMP_DEFAULT_ACCELERATOR в том случае, если оно задано.  
  
3.  В противном случае —-эмулируемого устройства.  
  
4.  В противном случае — устройство, которое имеет наибольшее количество доступной памяти.  
  
5.  В противном случае — устройства, который не присоединен к отображаемому.  
  
 Кроме того, среда выполнения определяет `access_type` из `access_type_auto` для сочетания клавиш по умолчанию. Это означает, что сочетания клавиш по умолчанию использует общей памяти, если он поддерживается и должен совпадать с выделенной памяти (не общими) известны его характеристики производительности (пропускной способности и задержки).  
  
 Свойства по умолчанию ускорителя можно определить, создав сочетания клавиш по умолчанию и проверка его свойств. В следующем примере кода выводится путь, объем памяти сочетаний клавиш, поддержки общей памяти, поддержка двойной точности и ограниченная поддержка двойной точности по умолчанию ускорителя.  
  
```cpp  
 
void default_properties() {  
    accelerator default_acc;  
    std::wcout <<default_acc.device_path <<"\n";  
    std::wcout <<default_acc.dedicated_memory <<"\n";  
    std::wcout <<(accs[i].supports_cpu_shared_memory    
 "CPU shared memory: true" : "CPU shared memory: false") <<"\n";  
    std::wcout <<(accs[i].supports_double_precision    
 "double precision: true" : "double precision: false") <<"\n";  
    std::wcout <<(accs[i].supports_limited_double_precision    
 "limited double precision: true" : "limited double precision: false") <<"\n";  
}  
 
```  
  
### <a name="cppampdefaultaccelerator-environment-variable"></a>Переменная среды CPPAMP_DEFAULT_ACCELERATOR  
 Можно задать для задания переменной среды CPPAMP_DEFAULT_ACCELERATOR `accelerator::device_path` по умолчанию ускорителя. Путь зависит от оборудования. В следующем коде используется `accelerator::get_all` функции для получения списка доступных ускорителей, а затем отображает путь и характеристики каждого сочетаний клавиш.  
  
```cpp  
 
void list_all_accelerators()  
{  
    std::vector<accelerator> accs = accelerator::get_all();
for (int i = 0; i <accs.size();

i++) {  
    std::wcout <<accs[i].device_path <<"\n";  
    std::wcout <<accs[i].dedicated_memory <<"\n";  
    std::wcout <<(accs[i].supports_cpu_shared_memory    
 "CPU shared memory: true" : "CPU shared memory: false") <<"\n";  
    std::wcout <<(accs[i].supports_double_precision    
 "double precision: true" : "double precision: false") <<"\n";  
    std::wcout <<(accs[i].supports_limited_double_precision    
 "limited double precision: true" : "limited double precision: false") <<"\n";  
 }  
}  
 
```  
  
## <a name="selecting-an-accelerator"></a>Выбор ускорителя  
 Чтобы выбрать ускоритель, используйте `accelerator::get_all` метод для получения списка доступных ускорителей и затем выберите один на основе его свойств. В этом примере показано, как выбрать сочетания клавиш, которое имеет наибольшее количество памяти:  
  
```cpp  
 
void pick_with_most_memory()  
{  
    std::vector<accelerator> accs = accelerator::get_all();
accelerator acc_chosen = accs[0];  
    for (int i = 0; i <accs.size();

i++) {  
    if (accs[i].dedicated_memory> acc_chosen.dedicated_memory) {  
    acc_chosen = accs[i];  
 }  
 }  
 
    std::wcout <<"The accelerator with the most memory is "    
 <<acc_chosen.device_path <<"\n"  
 <<acc_chosen.dedicated_memory <<".\n";  
}  
 
```  
  
> [!NOTE]
>  Один из сочетания клавиш, которые возвращаются `accelerator::get_all` — сочетание клавиш ЦП. Не удается выполнить код accelerator ЦП. Чтобы отфильтровать accelerator ЦП, сравните значение [device_path](../Topic/accelerator::device_path%20Data%20Member.md) Свойства ускорителя, возвращаемый `accelerator::get_all` со значением [accelerator::cpu_accelerator](../Topic/accelerator::cpu_accelerator%20Data%20Member.md). Дополнительные сведения см. в разделе «Специальные ускорители» в этой статье.  
  
## <a name="shared-memory"></a>Общая память  
 Общая память — это память, может осуществляться с Процессором и сочетания клавиш. Использование общей памяти устраняет или значительно уменьшает расходы на копирование данных между центральным Процессором и сочетания клавиш. Несмотря на то, что общий объем памяти, он не доступен одновременно центральным Процессором и сочетания клавиш, и благодаря этому поведение не определено. Свойства сочетаний клавиш [supports_cpu_shared_memory](../Topic/accelerator::supports_cpu_shared_memory%20Data%20Member.md) возвращает `true` Если сочетания клавиш поддерживает общей памяти и [default_cpu_access_type](../Topic/accelerator::default_cpu_access_type%20Data%20Member.md) свойство получает значение по умолчанию [access_type](../Topic/access_type%20Enumeration.md) для памяти, выделенной в `accelerator`— например, `array`связанные с `accelerator`, или `array_view` объектов, взаимодействующих с `accelerator`.  
  
 Среда выполнения C++ AMP автоматически выбирает лучший по умолчанию `access_type` для каждого `accelerator`, но характеристики производительности общей памяти (полосы пропускания и задержки) может быть хуже, чем памяти, выделенной accelerator (без общего доступа), при чтении из ЦП, записи из ЦП или оба. Если общая память выполняет и выделенной памяти для чтения и записи с ЦП, среда выполнения по умолчанию `access_type_read_write`; в противном случае, среда выполнения выбирает меньшем по умолчанию `access_type`, и позволяет приложению переопределить его, если шаблоны доступа к памяти, ядер его вычисление выгоды от другой `access_type`.  
  
 В следующем примере кода показано, как определить, является ли сочетания клавиш по умолчанию поддерживает общей памяти, а затем переопределяет его тип доступа по умолчанию и создает `accelerator_view` из него.  
  
```cpp  
#include <amp.h>  
#include <iostream>  
  
using namespace Concurrency;  
  
int main()  
{  
  accelerator acc = accelerator(accelerator::default_accelerator);  
  
  // Early out if the default accelerator doesn’t support shared memory.  
  if(!acc.supports_cpu_shared_memory)  
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
  
  `accelerator_view` Всегда отражает `default_cpu_access_type` из `accelerator` он связан, а также интерфейс не переопределить или изменить его `access_type`.  
  
## <a name="changing-the-default-accelerator"></a>Изменение сочетания клавиш по умолчанию  
 Сочетания клавиш по умолчанию можно изменить путем вызова `accelerator::set_default` метод. Сочетания клавиш по умолчанию можно изменить только в том случае, когда для каждого приложения выполнения и вам необходимо изменить его перед выполнением любого кода в GPU. Возвращать все последующие вызовы изменять сочетания клавиш `false`. Если вы хотите использовать различных сочетаний клавиш в вызове `parallel_for_each`, ознакомьтесь с разделом «Использование нескольких ускорители» в этой статье. В следующем примере кода задается по умолчанию ускорителя не эмулируется, не подключен на экран, а также поддерживает двойной точности.  
  
```cpp  
 
    bool pick_accelerator()  
{  
    std::vector<accelerator> accs = accelerator::get_all();
accelerator chosen_one;  
 
    auto result = 
    std::find_if(accs.begin(), accs.end(), [] (const accelerator& acc)  
 {  
    return !acc.is_emulated&& 
    acc.supports_double_precision&& 
 !acc.has_display;  
 });

 
    if (result != accs.end())  
    chosen_one = *(result);

 
    std::wcout <<chosen_one.description <<std::endl;  
 
    bool success = accelerator::set_default(chosen_one.device_path);

    return success;  
}  
 
```  
  
## <a name="using-multiple-accelerators"></a>Использование нескольких ускорителей  
 Можно использовать несколько акселераторы в приложении двумя способами:  
  
-   Можно передать `accelerator_view` объектов вызовы [parallel_for_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md) метод.  
  
-   Можно создать `array` объекта с помощью определенной `accelerator_view` объекта. Среда выполнения C + AMP берет `accelerator_view` объекта из записанные `array` объекта в лямбда-выражение.  
  
## <a name="special-accelerators"></a>Специальные ускорители  
 Пути устройства три специальные ускорителей доступны как свойства `accelerator` класса:  
  
- [Элемент данных Accelerator::direct3d_ref](../Topic/accelerator::direct3d_ref%20Data%20Member.md): это решение однопоточных использует программное обеспечение на ЦП для эмуляции универсального видеокарты. Он используется по умолчанию для отладки, но не имеет смысла в производственной среде, так как он работает медленнее, чем аппаратных ускорителей. Кроме того он доступен только в DirectX SDK и пакета Windows SDK и маловероятно, должны быть установлены на компьютерах ваших заказчиков. Дополнительные сведения см. в разделе [отладки кода GPU](../Topic/Debugging%20GPU%20Code.md).  
  
- [Элемент данных Accelerator::direct3d_warp](../Topic/accelerator::direct3d_warp%20Data%20Member.md): это решение предоставляет резервное решение о выполнении кода C++ AMP на многоядерных процессорах, использующих Streaming SIMD Extensions (SSE).  
  
- [элемент данных Accelerator::cpu_accelerator](../Topic/accelerator::cpu_accelerator%20Data%20Member.md): это решение можно использовать для настройки промежуточных массивов. Оно не может выполнять код C++ AMP. Дополнительные сведения см. в разделе [промежуточной массивов в C++ AMP](http://go.microsoft.com/fwlink/p/LinkId=248485) блога по параллельному программированию в блоге машинного кода.  
  
## <a name="interoperability"></a>Взаимодействие  
 Среда выполнения C++ AMP поддерживает взаимодействие между `accelerator_view` класса и Direct3D [ID3D11Device интерфейс](http://go.microsoft.com/fwlink/p/LinkId=248488).  [Create_accelerator_view](../Topic/create_accelerator_view%20Function.md) принимает `IUnknown` интерфейс и возвращает `accelerator_view` объекта.  [Get_device](http://msdn.microsoft.com/ru-ru/8194125e-8396-4d62-aa8a-65831dea8439) принимает `accelerator_view` объекта и возвращает `IUknown` интерфейса.  
  
## <a name="see-also"></a>См. также  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [Отладка кода GPU](../Topic/Debugging%20GPU%20Code.md)   
 [Класс accelerator_view](../Topic/accelerator_view%20Class.md)
