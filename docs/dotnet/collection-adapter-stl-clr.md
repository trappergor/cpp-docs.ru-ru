---
title: "collection_adapter (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::collection_adapter
dev_langs: C++
helpviewer_keywords: collection_adapter class [STL/CLR]
ms.assetid: 31964058-1f50-48bf-82c2-b0b3cc8a7887
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4a1a03dd6ecc52cd3921428e681fe5affa11d275
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="collectionadapter-stlclr"></a>collection_adapter (STL/CLR)
Инкапсулирует коллекцию .NET для использования в качестве контейнера STL/CLR. Объект `collection_adapter` — это класс шаблона, описывающий простого объекта-контейнера STL/CLR. Он инкапсулирует интерфейс библиотеки базовых классов (BCL) и возвращает пару итератор, который позволяет управлять управляемой последовательности.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Coll>  
    ref class collection_adapter;  
  
template<>  
    ref class collection_adapter<  
        System::Collections::ICollection>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IEnumerable>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IList>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IDictionary>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::ICollection<Value>>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IEnumerable<Value>>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IList<Value>>;  
template<typename Key,  
    typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IDictionary<Key, Value>>;  
```  
  
#### <a name="parameters"></a>Параметры  
 Свер  
 Тип упакованного коллекции.  
  
## <a name="specializations"></a>Специализации  
  
|Специализация|Описание:|  
|--------------------|-----------------|  
|IEnumerable|Последовательности элементов.|  
|ICollection|Поддерживает группу элементов.|  
|Интерфейс IList|Сохраняет упорядоченную группу элементов.|  
|IDictionary|Совокупность {ключ, значение} пары.|  
|Интерфейс IEnumerable\<значение >|Последовательности типизированных элементов.|  
|ICollection\<значение >|Поддерживает группу типизированных элементов.|  
|IList\<значение >|Сохраняет упорядоченную группу типизированных элементов.|  
|IDictionary\<значение >|Поддерживает набор типизированных {ключ, значение} пары.|  
  
## <a name="members"></a>Участники  
  
|Определение типа|Описание:|  
|---------------------|-----------------|  
|[collection_adapter::difference_type (STL/CLR)](../dotnet/collection-adapter-difference-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[collection_adapter::iterator (STL/CLR)](../dotnet/collection-adapter-iterator-stl-clr.md)|Тип итератора для управляемой последовательности.|  
|[collection_adapter::key_type (STL/CLR)](../dotnet/collection-adapter-key-type-stl-clr.md)|Тип ключа словаря.|  
|[collection_adapter::mapped_type (STL/CLR)](../dotnet/collection-adapter-mapped-type-stl-clr.md)|Тип значения словаря.|  
|[collection_adapter::reference (STL/CLR)](../dotnet/collection-adapter-reference-stl-clr.md)|Тип ссылки на элемент.|  
|[collection_adapter::size_type (STL/CLR)](../dotnet/collection-adapter-size-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[collection_adapter::value_type (STL/CLR)](../dotnet/collection-adapter-value-type-stl-clr.md)|Тип элемента.|  
  
|Функция-член|Описание:|  
|---------------------|-----------------|  
|[collection_adapter::base (STL/CLR)](../dotnet/collection-adapter-base-stl-clr.md)|Обозначает упакованного интерфейса BCL.|  
|[collection_adapter::begin (STL/CLR)](../dotnet/collection-adapter-begin-stl-clr.md)|Задает начало управляемой последовательности.|  
|[collection_adapter::collection_adapter (STL/CLR)](../dotnet/collection-adapter-collection-adapter-stl-clr.md)|Создает объект адаптера.|  
|[collection_adapter::end (STL/CLR)](../dotnet/collection-adapter-end-stl-clr.md)|Задает конец управляемой последовательности.|  
|[collection_adapter::size (STL/CLR)](../dotnet/collection-adapter-size-stl-clr.md)|Подсчитывает количество элементов.|  
|[collection_adapter::swap (STL/CLR)](../dotnet/collection-adapter-swap-stl-clr.md)|Меняет местами содержимое двух контейнеров.|  
  
|Оператор|Описание:|  
|--------------|-----------------|  
|[collection_adapter::operator= (STL/CLR)](../dotnet/collection-adapter-operator-assign-stl-clr.md)|Заменяет дескриптор хранимых BCL.|  
  
## <a name="remarks"></a>Примечания  
 Используйте этот класс шаблона для управления BCL контейнера в качестве контейнера STL/CLR. `collection_adapter` Сохраняет дескриптор BCL интерфейс, который в свою очередь, управляющий последовательностью элементов. Объект `collection_adapter` объекта `X` возвращает пару итераторов ввода `X.begin()` и `X.end()` использовать посетить элементы, по порядку. Некоторые специализации также позволяют записывать `X.size()` для определения длины управляемой последовательности.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext адаптер >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)   
 [make_collection (STL/CLR)](../dotnet/make-collection-stl-clr.md)