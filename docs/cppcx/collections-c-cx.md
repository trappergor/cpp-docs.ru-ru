---
title: Коллекции (C + +/ CX) | Документы Microsoft
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 914da30b-aac5-4cd7-9da3-a5ac08cdd72c
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0296422ce0f9ef49b096d5ea8512530871fc733b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="collections-ccx"></a>Коллекции (C++/CX)
В C + +/ CX программы, можно сделать свободно пользоваться контейнерами библиотеки стандартных шаблонов (STL) и любыми другими типами пользовательских коллекций. Однако при передаче коллекции и обратно через двоичный интерфейс приложений (ABI) среды выполнения Windows — например, элементу управления XAML или клиенту JavaScript, необходимо использовать типы коллекций среды выполнения Windows.  
  
 Среда выполнения Windows определены интерфейсы коллекций и связанных типов и C + +/ CX предоставлены конкретные реализации C++ в файле заголовка collection.h. На этой иллюстрации показаны связи между типами коллекций:  
  
 ![C&#43;&#43;&#47;дерева наследования CX для типов коллекций](../cppcx/media/cppcxcollectionsinheritancetree.png "CPPCXCollectionsInheritanceTree")  
  
-   [Класс Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) похож на [класс std::vector](../standard-library/vector-class.md).  
  
-   [Класс Platform::Collections::Map](../cppcx/platform-collections-map-class.md) похож на [класс std::map](../standard-library/map-class.md).  
  
-   [Класс Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md) и[класс Platform::Collections::MapView](../cppcx/platform-collections-mapview-class.md) являются доступными только для чтения версиями `Vector` и `Map`.  
  
-   Итераторы определяются в [пространстве имен Platform::Collections](../cppcx/platform-collections-namespace.md). Эти итераторы удовлетворяют требованиям итераторов STL и позволяют использовать алгоритмы [std::find](../standard-library/algorithm-functions.md#find),  [std::count_if](../standard-library/algorithm-functions.md#count_if)и другие алгоритмы STL в любом типе интерфейса [Windows::Foundation::Collections](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.aspx) или конкретном типе [Platform::Collections](../cppcx/platform-collections-namespace.md) . Например это означает, что можно выполнять перебор коллекции в компоненте среды выполнения Windows, которая создается в C# и применять к ней алгоритм STL.  
  
    > [!IMPORTANT]
    >  Итераторы прокси-сервера `VectorIterator` и `VectorViewIterator` используют прокси-объекты `VectoryProxy<T>` и `ArrowProxy<T>` для включения использования с контейнерами STL. Дополнительные сведения см. в теме "Элементы VectorProxy" далее в этой статье.  
  
-   C + +/ CX коллекции типов поддерживают, те же гарантии потокобезопасности, поддерживает контейнеры STL.  
  
-   [Windows::Foundation::Collections::IObservableVector](http://msdn.microsoft.com/library/windows/apps/br226052.aspx) и [Windows::Foundation::Collections::IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx) определяют события, инициируемые при разнообразных изменениях коллекции. Реализуя эти интерфейсы, объекты  [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) и [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) поддерживают привязку данных с коллекциями XAML. Например, если имеется объект `Vector` , данные которого связаны с `Grid`, то при добавлении данных в коллекцию их изменения отражаются в пользовательском интерфейсе таблицы.  
  
## <a name="vector-usage"></a>Использование класса Vector  
 Если класс должен передать контейнер последовательности в другой компонент среды выполнения Windows, используйте [Windows::Foundation:: Collections:: IVector\<T >](http://msdn.microsoft.com/library/windows/apps/br206631.aspx) как параметр или тип возвращаемого значения и [платформы:: Collections::vector\<T >](../cppcx/platform-collections-vector-class.md) качестве конкретной реализации. При попытке использования типа `Vector` в качестве открытого возвращаемого значения или параметра возникнет ошибка компилятора C3986. Эту ошибку можно исправить, заменив `Vector` объектом `IVector`.  
  
> [!IMPORTANT]
>  В случае передачи последовательности внутри разрабатываемой программы используйте `Vector` или `std::vector`, поскольку они более эффективны по сравнению с `IVector`. Используйте `IVector` только при передаче контейнера с помощью ABI.  
>   
>  Система типов среды выполнения Windows не поддерживает концепцию массивов массивов и поэтому невозможно передать IVector < Platform::Array\<T >> в качестве возвращаемого значения или параметра метода. Для передачи массива массивов или последовательности массивов в ABI используйте `IVector<IVector<T>^>`.  
  
 Класс `Vector<T>` предоставляет методы, необходимые для добавления и удаления элементов коллекции и доступа к ним. Его можно неявно преобразовать в класс `IVector<T>`. Алгоритмы STL также можно применять к экземплярам `Vector<T>`. В следующем примере демонстрируются некоторые простейшие варианты использования. [Функция начала](../cppcx/begin-function.md) и [функция окончания](../cppcx/end-function.md) , используемые здесь, — из пространства имен `Platform::Collections` , а не `std` .  
  
 [!code-cpp[cx_collections#01](../cppcx/codesnippet/CPP/collections/class1.cpp#01)]  
  
 При наличии существующего кода, использующего `std::vector` и вы хотите использовать его в компонент среды выполнения Windows, просто воспользуйтесь одним из `Vector` конструкторов, которые принимают `std::vector` или пару итераторов для создания `Vector` в той точке, где передается Коллекция через интерфейс ABI. В следующем примере показано использование конструктора класса `Vector` для эффективной инициализации из объекта `std::vector`. После операции перемещения исходная переменная `vec` более не является допустимой.  
  
 [!code-cpp[cx_collections#02](../cppcx/codesnippet/CPP/collections/class1.cpp#02)]  
  
 Если имеется вектор строк, которые должны будут передаваться через интерфейс ABI, необходимо решить, следует ли изначально создавать строки как типы `std::wstring` или как типы `Platform::String^`. Если предполагается выполнение большого объема операций с этими строками, используйте тип `wstring`. В противном случае создайте строки типа `Platform::String^` , чтобы избежать издержек, связанных с их последующим преобразованием. Кроме того, необходимо определить, куда лучше поместить строки для внутреннего использования — в `std:vector` или в `Platform::Collections::Vector`. В общем случае рекомендуется использовать объект `std::vector` и создавать из него `Platform::Vector` только при передаче контейнера через интерфейс ABI.  
  
## <a name="value-types-in-vector"></a>Типы значений в объекте Vector  
 Любой элемент, который необходимо сохранить в объекте [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) , должен поддерживать сравнение на равенство (неявно или с помощью пользовательского алгоритма сравнения [std::equal_to](../standard-library/equal-to-struct.md) ). Все ссылочные типы и все скалярные типы неявно поддерживают сравнение на равенство. Для нескалярных типов значений, таких как [Windows::FoundationDateTime](http://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx), или для пользовательских сравнений (например, `objA->UniqueID == objB->UniqueID`) необходимо предоставить специальный объект функции.  
   
  
## <a name="vectorproxy-elements"></a>Элементы VectorProxy  
 [Platform::Collections:: vectoriterator](../cppcx/platform-collections-vectoriterator-class.md) и [Platform::Collections:: vectorviewiterator](../cppcx/platform-collections-vectorviewiterator-class.md) позволяют использовать `range for` циклы и алгоритмы, такие как [std::sort](../standard-library/algorithm-functions.md#sort) с [ IVector\<T >](http://msdn.microsoft.com/en-us/library/windows/apps/br206631.aspx) контейнера. Однако невозможно получить доступ к элементам `IVector` через отмену ссылки на указатель C++; доступ к ним можно получить только с использованием методов [GetAt](http://msdn.microsoft.com/library/windows/apps/br206634.aspx) и [SetAt](http://msdn.microsoft.com/library/windows/apps/br206642.aspx) . Следовательно, эти итераторы используют прокси-классы `Platform::Details::VectorProxy<T>` и `Platform::Details::ArrowProxy<T>` для предоставления доступа к отдельным элементам с использованием операторов `*`, `->`и `[]` в соответствии с требованиями STL. Строго говоря, при использовании `IVector<Person^> vec`типом `*begin(vec)` является `VectorProxy<Person^>`. Однако прокси-объект практически всегда прозрачен для кода. Эти прокси-объекты не документируются, поскольку предназначены исключительно для внутреннего пользования итераторами, однако полезно иметь представление о самом механизме работы.  
  
 При использовании цикла `range for` с контейнерами `IVector` используйте `auto&&` для включения переменной итератора для правильной привязки к элементам `VectorProxy` . При использовании `auto` или `auto&`создается предупреждение компилятора С4239, а `VectoryProxy` упоминается в тексте предупреждения.  
  
 На следующем рисунке показан цикл `range for` с контейнерами `IVector<Person^>`. Обратите внимание, что выполнение прекращается в точке останова на строке 64. В окне **Быстрая проверка** показано, что переменная итератора `p` , по сути, является объектом `VectorProxy<Person^>` с переменными-членами `m_v` и `m_i` . Однако при вызове `GetType` для этой переменной она возвращает идентичный тип в экземпляр `Person` `p2`. Отсюда вывод: несмотря на то что `VectorProxy` и `ArrowProxy` могут отображаться в разделе **Быстрая проверка**, отладчик устраняет некоторые ошибки в компиляторе или других местах, для которых, как правило, не нужно явно создавать код.  
  
 ![VectorProxy в диапазоне&#45;цикла for](../cppcx/media/vectorproxy-1.png "VectorProxy_1")  
  
 Один из сценариев, в котором необходимо создать код для прокси-объекта, заключается в следующем: необходимо выполнить операцию `dynamic_cast` с элементами, например при поиске объектов XAML определенного типа в коллекции элементов `UIElement`. В этом случае необходимо сначала привести элемент к [Platform::Object](../cppcx/platform-object-class.md)^, а затем выполнить динамическое приведение.  
  
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
  
## <a name="map-usage"></a>Использование класса Map  
 В этом примере показано, как вставлять элементы и находить их в объекте [Platform::Collections::Map](../cppcx/platform-collections-map-class.md), а затем возвращать объект `Map` в качестве доступного только для чтения типа [Windows::Foundation::Collections::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx) .  
  
 [!code-cpp[cx_collections#04](../cppcx/codesnippet/CPP/collections/class1.cpp#04)]  
  
 Как правило, для реализации внутренних возможностей сопоставления предпочтительно использовать тип `std::map` (из соображений производительности). Если необходимо передать контейнер с помощью интерфейса ABI, создайте объект [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) из [std::map](../standard-library/map-class.md) и верните `Map` в качестве [Windows::Foundation::Collections::IMap](http://msdn.microsoft.com/library/windows/apps/br226042.aspx). При попытке использования типа `Map` в качестве открытого возвращаемого значения или параметра возникнет ошибка компилятора C3986. Эту ошибку можно исправить, заменив `Map` объектом `IMap`. В некоторых случаях (например, если вы не выполняете большого количества операций поиска или вставки и часто передаете коллекцию через интерфейс ABI) более рационально использовать класс `Platform::Collections::Map` с самого начала, не затрачивая ресурсы на преобразование типа объекта `std::map`. В любом случае следует избегать операций поиска и вставки в объектах `IMap`, поскольку из всех трех типов он обладает самой низкой производительностью. Преобразование в `IMap` следует выполнять только в момент передачи контейнера через интерфейс ABI.  
  
## <a name="value-types-in-map"></a>Типы значений в объекте Map  
 Элементы в [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) упорядочены. Любой элемент, который необходимо сохранить в объекте `Map` , должен поддерживать сравнение "меньше" для строгого слабого порядка (неявно или с помощью пользовательского алгоритма сравнения [stl::less](../standard-library/less-struct.md) ). Скалярные типы поддерживают сравнение неявно. Для нескалярных типов значений, таких как `Windows::Foundation::DateTime`, или для пользовательских вариантов сравнения (например, `objA->UniqueID < objB->UniqueID`) необходимо определять специальный алгоритм сравнения.  
  
## <a name="collection-types"></a>Типы коллекций  
 Коллекции подразделяются на четыре категории: изменяемые и доступные только для чтения версии последовательных и ассоциативных коллекций. Кроме того, C + +/ CX повышает функциональные возможности коллекций, предоставляя три класса итераторов, упрощающих доступ к коллекции. 
  
 Элементы изменяемой коллекции можно изменять, тогда как к элементам коллекции, доступной только для чтения (также называемой *представлением*), можно обращаться только для чтения. Элементы [Platform::Collections:: vector](../cppcx/platform-collections-vector-class.md) или[Platform::Collections:: vectorview](../cppcx/platform-collections-vectorview-class.md) коллекции возможен с помощью итератора или ее [Vector::GetAt](../cppcx/platform-collections-vector-class.md#getat) и индекса. Элементам ассоциативной коллекции можно обращаться с помощью коллекции [Map::Lookup](../cppcx/platform-collections-map-class.md#lookup) и ключ.  
  
 [Класс Platform::Collections::Map](../cppcx/platform-collections-map-class.md)  
 Изменяемая ассоциативная коллекция. Элементы объекта Map представляют собой пары "ключ-значение". Поддерживается как поиск значения по связанному с ним ключу, так и перебор всех пар "ключ-значение".  
  
 В классах `Map` и `MapView` используется шаблон `<K, V, C = std::less<K>>`; таким образом, алгоритм сравнения можно изменять.  Кроме того, в классах `Vector` и `VectorView` используется шаблон `<T, E = std::equal_to<T>>`, поэтому поведение метода `IndexOf()` можно изменять. Это важно в основном для объектов `Vector` и `VectorView`, содержащих структуры значения. Например, чтобы создать объект Vector\<Windows::Foundation:: DateTime >, необходимо предоставить пользовательский алгоритм сравнения, поскольку класс DateTime не перегружает оператор ==.  
  
 [класс Platform::Collections::MapView](../cppcx/platform-collections-mapview-class.md)  
 Версия объекта `Map`только для чтения.  
  
 [Platform::Collections::Vector Class](../cppcx/platform-collections-vector-class.md)  
 Изменяемая коллекция последовательностей. Класс`Vector<T>` поддерживает операции произвольного доступа, занимающие фиксированное время, и операции [добавления](../cppcx/platform-collections-vector-class.md#append) , занимающие фиксированное время с поправкой на амортизацию.  
  
 [Класс Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md)  
 Версия объекта `Vector` только для чтения.  
  
 [Класс Platform::Collections::InputIterator](../cppcx/platform-collections-inputiterator-class.md)  
 Итератор STL, отвечающий требованиям итератора ввода STL.  
  
 [Класс Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md)  
 Итератор STL, отвечающий требованиям изменяемого итератора произвольного доступа STL.  
  
 [Класс Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md)  
 Итератор STL, отвечающий требованиям неизменного (`const`) итератора произвольного доступа STL.  
  
### <a name="begin-and-end-functions"></a>Функции begin() и end()  
 Чтобы упростить использование STL для обработки `Vector`, `VectorView`, `Map`, `MapView`и произвольных `Windows::Foundation::Collections` объектов, C + +/ CX поддерживает перегрузки функций [функция начала](../cppcx/begin-function.md) и [end Функция](../cppcx/end-function.md) не являющихся членами.  
  
 В следующей таблице перечислены все доступные итераторы и функции.  
  
|Iterators|Функции|  
|---------------|---------------|  
|[Platform::Collections:: vectoriterator\<T >](../cppcx/platform-collections-vectoriterator-class.md)<br /><br /> (Внутренне хранит [Windows::Foundation:: Collections:: IVector\<T >](http://msdn.microsoft.com/library/windows/apps/br206631.aspx) и int.)|[Начать](../cppcx/begin-function.md)/ [окончания](../cppcx/end-function.md)([Windows::Foundation:: Collections:: IVector\<T >](http://msdn.microsoft.com/library/windows/apps/br206631.aspx))|  
|[Platform::Collections::VectorViewIterator\<T>](../cppcx/platform-collections-vectorviewiterator-class.md)<br /><br /> (Внутренне хранит [IVectorView\<T >](http://msdn.microsoft.com/library/windows/apps/br226058.aspx)^ и int.)|[Начать](../cppcx/begin-function.md)/ [окончания](../cppcx/end-function.md) ([IVectorView\<T >](http://msdn.microsoft.com/library/windows/apps/br226058.aspx)^)|  
|[Platform::Collections:: inputiterator\<T >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (Внутренне хранит [IIterator\<T >](http://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ и T.)|[Начать](../cppcx/begin-function.md)/ [окончания](../cppcx/end-function.md) ([IIterable\<T >](http://msdn.microsoft.com/library/windows/apps/br226024.aspx))|  
|[Platform::Collections:: inputiterator < IKeyValuePair\<K, V > ^ >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (Внутренне хранит [IIterator\<T >](http://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ и T.)|[Начать](../cppcx/begin-function.md)/ [окончания](../cppcx/end-function.md) ([IMap\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226042.aspx).|  
|[Platform::Collections:: inputiterator < IKeyValuePair\<K, V > ^ >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (Внутренне хранит [IIterator\<T >](http://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ и T.)|[begin](../cppcx/begin-function.md)/ [end](../cppcx/end-function.md) ([Windows::Foundation::Collections::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx))|  
  
### <a name="collection-change-events"></a>События изменения коллекций  
 Классы `Vector` и `Map` поддерживают привязку данных в коллекциях XAML за счет реализации событий, которые возникают при изменении или сбросе объекта коллекции, а также при вставке, удалении или изменении любого элемента коллекции. Можно разрабатывать собственные типы, поддерживающие привязку данных, но нельзя наследовать от типов `Map` и `Vector` , так как эти типы запечатаны.  
  
 Делегаты [Windows::Foundation::Collections::VectorChangedEventHandler](http://msdn.microsoft.com/library/windows/apps/br206656.aspx) и [Windows::Foundation::Collections::MapChangedEventHandler](http://msdn.microsoft.com/library/windows/apps/br206644.aspx) определяют сигнатуры для обработчиков событий для событий изменения коллекции. Открытый класс перечисления [Windows::Foundation::Collections::CollectionChange](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx) и ссылочные классы `Platform::Collection::Details::MapChangedEventArgs` и `Platform::Collections::Details::VectorChangedEventArgs` хранят аргументы события, по которым можно определить его причину. Типы *`EventArgs` определены в пространстве имен `Details`, поскольку нет необходимости создавать и использовать их явно при использовании классов `Map` и `Vector`.  
  
## <a name="see-also"></a>См. также  
 [Система типов](../cppcx/type-system-c-cx.md)   
 [Встроенные типы](http://msdn.microsoft.com/en-us/acc196fd-09da-4882-b554-6c94685ec75f)   
 [Справочник по языку Visual C++](../cppcx/visual-c-language-reference-c-cx.md)   
 [Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)