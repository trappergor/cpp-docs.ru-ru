---
title: "Коллекции (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 914da30b-aac5-4cd7-9da3-a5ac08cdd72c
caps.latest.revision: 35
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 35
---
# Коллекции (C++/CX)
В программе [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) можно свободно пользоваться контейнерами библиотеки стандартных шаблонов \(STL\) и любыми другими пользовательскими типами коллекций. Однако при передаче коллекции через границы интерфейса ABI приложения [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] \(например, элементу управления XAML или клиенту JavaScript\) необходимо использовать типы коллекций [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)].  
  
 В [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] определены интерфейсы коллекций и связанных типов, и в [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] предоставлены конкретные реализации C\+\+ в файле заголовка collection.h. На этой иллюстрации показаны связи между типами коллекций:  
  
 ![Дерево наследования C&#43;&#43;&#47;CX для типов коллекций](../cppcx/media/cppcxcollectionsinheritancetree.png "CPPCXCollectionsInheritanceTree")  
  
-   [Класс Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) похож на [класс std::vector](../Topic/vector%20Class%201.md).  
  
-   [Класс Platform::Collections::Map](../cppcx/platform-collections-map-class.md) похож на [класс std::map](../standard-library/map-class.md).  
  
-   [Класс Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md) и[класс Platform::Collections::MapView](../cppcx/platform-collections-mapview-class.md) являются доступными только для чтения версиями `Vector` и `Map`.  
  
-   Итераторы определяются в [пространстве имен Platform::Collections](../cppcx/platform-collections-namespace.md). Эти итераторы удовлетворяют требованиям итераторов STL и позволяют использовать алгоритмы [std::find](http://msdn.microsoft.com/library/021e9ef9-8817-409f-92ee-cd7104867361), [std::count\_if](http://msdn.microsoft.com/library/b785887c-83cd-4099-becc-3284dee05295) и другие алгоритмы STL в любом типе интерфейса [Windows::Foundation::Collections](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.aspx) или конкретном типе [Platform::Collections](../cppcx/platform-collections-namespace.md). Например, это означает, что можно выполнять перебор коллекции в компоненте [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], созданном на языке C\#, и применять к ней алгоритмы STL.  
  
    > [!IMPORTANT]
    >  Итераторы прокси\-сервера `VectorIterator` и `VectorViewIterator` используют прокси\-объекты `VectoryProxy<T>` и `ArrowProxy<T>` для включения использования с контейнерами STL. Дополнительные сведения см. в теме "Элементы VectorProxy" далее в этой статье.  
  
-   Типы коллекций [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] обеспечивают те же гарантии потокобезопасности, что и контейнеры STL.  
  
-   [Windows::Foundation::Collections::IObservableVector](http://msdn.microsoft.com/library/windows/apps/br226052.aspx) и [Windows::Foundation::Collections::IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx) определяют события, инициируемые при разнообразных изменениях коллекции. Реализуя эти интерфейсы, объекты [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) и [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) поддерживают привязку данных с коллекциями XAML. Например, если имеется объект `Vector`, данные которого связаны с `Grid`, то при добавлении данных в коллекцию их изменения отражаются в пользовательском интерфейсе таблицы.  
  
## Использование класса Vector  
 Если класс должен передать контейнер последовательности в другой компонент [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], используйте [Windows::Foundation::Collections::IVector\<T\>](http://msdn.microsoft.com/library/windows/apps/br206631.aspx) в качестве параметра или возвращаемого типа, а [Platform::Collections::Vector\<T\>](../cppcx/platform-collections-vector-class.md) — в качестве конкретной реализации. При попытке использования типа `Vector` в качестве открытого возвращаемого значения или параметра возникнет ошибка компилятора C3986. Эту ошибку можно исправить, заменив `Vector` объектом `IVector`.  
  
> [!IMPORTANT]
>  В случае передачи последовательности внутри разрабатываемой программы используйте `Vector` или `std::vector`, поскольку они более эффективны по сравнению с `IVector`. Используйте `IVector` только при передаче контейнера с помощью ABI.  
>   
>  Система типов среды выполнения Windows не поддерживает концепцию массивов массивов и, таким образом, невозможно передать IVector\<Platform::Array\<T\>\> в качестве возвращаемого значения или параметра метода. Для передачи массива массивов или последовательности массивов в ABI используйте `IVector<IVector<T>^>`.  
  
 Класс `Vector<T>` предоставляет методы, необходимые для добавления и удаления элементов коллекции и доступа к ним. Его можно неявно преобразовать в класс `IVector<T>`. Алгоритмы STL также можно применять к экземплярам `Vector<T>`. В следующем примере демонстрируются некоторые простейшие варианты использования.[Функция начала](../cppcx/begin-function.md) и [функция окончания](../cppcx/end-function.md), используемые здесь, — из пространства имен `Platform::Collections`, а не `std`.  
  
 [!code-cpp[cx_collections#01](../snippets/cpp/VS_Snippets_Misc/cx_collections/cpp/class1.cpp#01)]  
  
 Если имеется существующий код, который использует `std::vector`, и требуется использовать его в компоненте [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], просто воспользуйтесь одним из конструкторов класса `Vector`, принимающим объект `std::vector` или пару итераторов в качестве аргументов и создающим экземпляр класса `Vector` в точке, где коллекция передается через интерфейс ABI. В следующем примере показано использование конструктора класса `Vector` для эффективной инициализации из объекта `std::vector`. После операции перемещения исходная переменная `vec` более не является допустимой.  
  
 [!code-cpp[cx_collections#02](../snippets/cpp/VS_Snippets_Misc/cx_collections/cpp/class1.cpp#02)]  
  
 Если имеется вектор строк, которые должны будут передаваться через интерфейс ABI, необходимо решить, следует ли изначально создавать строки как типы `std::wstring` или как типы `Platform::String^`. Если предполагается выполнение большого объема операций с этими строками, используйте тип `wstring`. В противном случае создайте строки типа `Platform::String^`, чтобы избежать издержек, связанных с их последующим преобразованием. Кроме того, необходимо определить, куда лучше поместить строки для внутреннего использования — в `std:vector` или в `Platform::Collections::Vector`. В общем случае рекомендуется использовать объект `std::vector` и создавать из него `Platform::Vector` только при передаче контейнера через интерфейс ABI.  
  
## Типы значений в объекте Vector  
 Любой элемент, который необходимо сохранить в объекте [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md), должен поддерживать сравнение на равенство \(неявно или с помощью пользовательского алгоритма сравнения [std::equal\_to](../standard-library/equal-to-struct.md)\). Все ссылочные типы и все скалярные типы неявно поддерживают сравнение на равенство. Для нескалярных типов значений, таких как [Windows::FoundationDateTime](http://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx), или для пользовательских сравнений \(например, `objA->UniqueID == objB->UniqueID`\) необходимо предоставить специальный объект функции.  
  
  
  
## Элементы VectorProxy  
 [Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md) и [Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md) позволяют использовать циклы и алгоритмы `range for`, такие как [std::sort](http://msdn.microsoft.com/library/9b0a4fc1-5131-4c73-9c2e-d72211f2d0ae), в контейнере [IVector\<T\>](http://msdn.microsoft.com/en-us/library/windows/apps/br206631.aspx). Однако невозможно получить доступ к элементам `IVector` через отмену ссылки на указатель C\+\+; доступ к ним можно получить только с использованием методов [GetAt](http://msdn.microsoft.com/library/windows/apps/br206634.aspx) и [SetAt](http://msdn.microsoft.com/library/windows/apps/br206642.aspx). Следовательно, эти итераторы используют прокси\-классы `Platform::Details::VectorProxy<T>` и `Platform::Details::ArrowProxy<T>` для предоставления доступа к отдельным элементам с использованием операторов `*`, `->` и `[]` в соответствии с требованиями STL. Строго говоря, при использовании `IVector<Person^> vec` типом `*begin(vec)` является `VectorProxy<Person^>`. Однако прокси\-объект практически всегда прозрачен для кода. Эти прокси\-объекты не документируются, поскольку предназначены исключительно для внутреннего пользования итераторами, однако полезно иметь представление о самом механизме работы.  
  
 При использовании цикла `range for` с контейнерами `IVector` используйте `auto&&` для включения переменной итератора для правильной привязки к элементам `VectorProxy`. При использовании `auto` или `auto&` создается предупреждение компилятора С4239, а `VectoryProxy` упоминается в тексте предупреждения.  
  
 На следующем рисунке показан цикл `range for` с контейнерами `IVector<Person^>`. Обратите внимание, что выполнение прекращается в точке останова на строке 64. В окне **Быстрая проверка** показано, что переменная итератора `p`, по сути, является объектом `VectorProxy<Person^>` с переменными\-членами `m_v` и `m_i`. Однако при вызове `GetType` для этой переменной она возвращает идентичный тип в экземпляр `Person``p2`. Отсюда вывод: несмотря на то что `VectorProxy` и `ArrowProxy` могут отображаться в разделе **Быстрая проверка**, отладчик устраняет некоторые ошибки в компиляторе или других местах, для которых, как правило, не нужно явно создавать код.  
  
 ![VectorProxy в диапазоне цикла for](../cppcx/media/vectorproxy-1.png "VectorProxy\_1")  
  
 Один из сценариев, в котором необходимо создать код для прокси\-объекта, заключается в следующем: необходимо выполнить операцию `dynamic_cast` с элементами, например при поиске объектов XAML определенного типа в коллекции элементов `UIElement`. В этом случае необходимо сначала привести элемент к [Platform::Object](../cppcx/platform-object-class.md)^, а затем выполнить динамическое приведение.  
  
```  
  
void FindButton(UIElementCollection^ col)  
{  
    // Use auto&& to avoid warning C4239  
    for (auto&& elem : col)  
    {  
        Button^ temp = dynamic_cast<Button^>(static_cast<Object^>(elem));  
        if (nullptr != temp)  
        {  
            // Use temp...  
        }  
    }  
}  
```  
  
## Использование класса Map  
 В этом примере показано, как вставлять элементы и находить их в объекте [Platform::Collections::Map](../cppcx/platform-collections-map-class.md), а затем возвращать объект `Map` в качестве доступного только для чтения типа [Windows::Foundation::Collections::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx).  
  
 [!code-cpp[cx_collections#04](../snippets/cpp/VS_Snippets_Misc/cx_collections/cpp/class1.cpp#04)]  
  
 Как правило, для реализации внутренних возможностей сопоставления предпочтительно использовать тип `std::map` \(из соображений производительности\). Если необходимо передать контейнер с помощью интерфейса ABI, создайте объект [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) из [std::map](../standard-library/map-class.md) и верните `Map` в качестве [Windows::Foundation::Collections::IMap](http://msdn.microsoft.com/library/windows/apps/br226042.aspx). При попытке использования типа `Map` в качестве открытого возвращаемого значения или параметра возникнет ошибка компилятора C3986. Эту ошибку можно исправить, заменив `Map` объектом `IMap`. В некоторых случаях \(например, если вы не выполняете большого количества операций поиска или вставки и часто передаете коллекцию через интерфейс ABI\) более рационально использовать класс `Platform::Collections::Map` с самого начала, не затрачивая ресурсы на преобразование типа объекта `std::map`. В любом случае следует избегать операций поиска и вставки в объектах `IMap`, поскольку из всех трех типов он обладает самой низкой производительностью. Преобразование в `IMap` следует выполнять только в момент передачи контейнера через интерфейс ABI.  
  
## Типы значений в объекте Map  
 Элементы в [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) упорядочены. Любой элемент, который необходимо сохранить в объекте `Map`, должен поддерживать сравнение "меньше" для строгого слабого порядка \(неявно или с помощью пользовательского алгоритма сравнения [stl::less](../standard-library/less-struct.md)\). Скалярные типы поддерживают сравнение неявно. Для нескалярных типов значений, таких как `Windows::Foundation::DateTime`, или для пользовательских вариантов сравнения \(например, `objA->UniqueID < objB->UniqueID`\) необходимо определять специальный алгоритм сравнения.  
  
## Типы коллекций  
 Коллекции подразделяются на четыре категории: изменяемые и доступные только для чтения версии последовательных и ассоциативных коллекций. Кроме того, [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] повышает функциональные возможности коллекций, предоставляя три класса итераторов, упрощающих доступ к коллекциям. Краткое описание итераторов см. в разделе [Итераторы](../standard-library/iterators.md).  
  
 Элементы изменяемой коллекции можно изменять, тогда как к элементам коллекции, доступной только для чтения \(также называемой *представлением*\), можно обращаться только для чтения. Доступ к элементам коллекции [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) или [Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md) можно получить с использованием итератора или объекта [Vector::GetAt \- метод](../cppcx/vector-getat-method.md) коллекции и индекса. К элементам ассоциативной коллекции можно обращаться с помощью ее метода [Метод Map::Lookup](../cppcx/map-lookup-method.md) и ключа.  
  
 [Класс Platform::Collections::Map](../cppcx/platform-collections-map-class.md)  
 Изменяемая ассоциативная коллекция. Элементы объекта Map представляют собой пары "ключ\-значение". Поддерживается как поиск значения по связанному с ним ключу, так и перебор всех пар "ключ\-значение".  
  
 В классах `Map` и `MapView` используется шаблон `<K, V, C = std::less<K>>`; таким образом, алгоритм сравнения можно изменять.  Кроме того, в классах `Vector` и `VectorView` используется шаблон `<T, E = std::equal_to<T>>`, поэтому поведение метода `IndexOf()` можно изменять. Это важно в основном для объектов `Vector` и `VectorView`, содержащих структуры значения. Например, чтобы создать объект Vector\<Windows::Foundation::DateTime\>, необходимо предоставить пользовательский алгоритм сравнения, поскольку класс DateTime не перегружает оператор \=\=.  
  
 [Класс Platform::Collections::MapView](../cppcx/platform-collections-mapview-class.md)  
 Версия объекта `Map` только для чтения.  
  
 [Класс Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md)  
 Изменяемая коллекция последовательностей. Класс `Vector<T>` поддерживает операции произвольного доступа, занимающие фиксированное время, и операции [добавления](../cppcx/vector-append-method.md), занимающие фиксированное время с поправкой на амортизацию.  
  
 [Класс Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md)  
 Версия объекта `Vector` только для чтения.  
  
 [Класс Platform::Collections::InputIterator](../cppcx/platform-collections-inputiterator-class.md)  
 Итератор STL, отвечающий требованиям итератора ввода STL.  
  
 [Класс Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md)  
 Итератор STL, отвечающий требованиям изменяемого итератора произвольного доступа STL.  
  
 [Класс Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md)  
 Итератор STL, отвечающий требованиям неизменного \(`const`\) итератора произвольного доступа STL.  
  
### Функции begin\(\) и end\(\)  
 Чтобы упростить использование STL для обработки объектов `Vector`, `VectorView`, `Map`, `MapView` и произвольных объектов `Windows::Foundation::Collections`, [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] поддерживает перегрузки функций [begin \- функция](../cppcx/begin-function.md) и [Функция end](../cppcx/end-function.md), не являющихся членами.  
  
 В следующей таблице перечислены все доступные итераторы и функции.  
  
|Итераторы|Функции|  
|---------------|-------------|  
|[Platform::Collections::VectorIterator\<T\>](../cppcx/platform-collections-vectoriterator-class.md)<br /><br /> \(Внутреннее хранение [Windows::Foundation::Collections:: IVector\<T\>](http://msdn.microsoft.com/library/windows/apps/br206631.aspx) и int.\)|[begin](../cppcx/begin-function.md)\/ [end](../cppcx/end-function.md)\([Windows::Foundation::Collections:: IVector\<T\>](http://msdn.microsoft.com/library/windows/apps/br206631.aspx)\)|  
|[Platform::Collections::VectorViewIterator\<T\>](../cppcx/platform-collections-vectorviewiterator-class.md)<br /><br /> \(Внутреннее хранение [IVectorView\<T\>](http://msdn.microsoft.com/library/windows/apps/br226058.aspx)^ и int.\)|[begin](../cppcx/begin-function.md)\/ [end](../cppcx/end-function.md) \([IVectorView\<T\>](http://msdn.microsoft.com/library/windows/apps/br226058.aspx)^\)|  
|[Platform::Collections::InputIterator\<T\>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> \(Внутреннее хранение [IIterator\<T\>](http://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ и T.\)|[begin](../cppcx/begin-function.md)\/ [end](../cppcx/end-function.md) \([IIterable\<T\>](http://msdn.microsoft.com/library/windows/apps/br226024.aspx)\)|  
|[Platform::Collections::InputIterator\<IKeyValuePair\<K, V\>^\>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> \(Внутреннее хранение [IIterator\<T\>](http://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ и T.\)|[begin](../cppcx/begin-function.md)\/ [end](../cppcx/end-function.md) \([IMap\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br226042.aspx).|  
|[Platform::Collections::InputIterator\<IKeyValuePair\<K, V\>^\>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> \(Внутреннее хранение [IIterator\<T\>](http://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ и T.\)|[begin](../cppcx/begin-function.md)\/ [end](../cppcx/end-function.md) \([Windows::Foundation::Collections::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx)\)|  
  
### События изменения коллекций  
 Классы `Vector` и `Map` поддерживают привязку данных в коллекциях XAML за счет реализации событий, которые возникают при изменении или сбросе объекта коллекции, а также при вставке, удалении или изменении любого элемента коллекции. Можно разрабатывать собственные типы, поддерживающие привязку данных, но нельзя наследовать от типов `Map` и `Vector`, так как эти типы запечатаны.  
  
 Делегаты [Windows::Foundation::Collections::VectorChangedEventHandler](http://msdn.microsoft.com/library/windows/apps/br206656.aspx) и [Windows::Foundation::Collections::MapChangedEventHandler](http://msdn.microsoft.com/library/windows/apps/br206644.aspx) определяют сигнатуры для обработчиков событий для событий изменения коллекции. Открытый класс перечисления [Windows::Foundation::Collections::CollectionChange](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx) и ссылочные классы  `Platform::Collection::Details::MapChangedEventArgs` и `Platform::Collections::Details::VectorChangedEventArgs` хранят аргументы события, по которым можно определить его причину. Типы \*`EventArgs` определены в пространстве имен `Details`, поскольку нет необходимости создавать и использовать их явно при использовании классов `Map` и `Vector`.  
  
## См. также  
 [Система типов](../cppcx/type-system-c-cx.md)   
 [Built\-in Types](http://msdn.microsoft.com/ru-ru/acc196fd-09da-4882-b554-6c94685ec75f)   
 [Справочник по языку C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)