---
title: End Function | Документация Майкрософт
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::end
dev_langs:
- C++
helpviewer_keywords:
- end Function
ms.assetid: fb837bff-fc76-4bae-9096-facf0e03041c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec25b92ca9ce21f72ff2fb573aae316ef1c19eac
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596654"
---
# <a name="end-function"></a>Функция end
Возвращает итератор, указывающий на позицию после конечного элемента коллекции, для доступа к которой используется указанный параметр интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
template <typename T>  
    ::Platform::Collections::VectorIterator<T>   
    end(  
        IVector<T>^ v       );  
  
template <typename T>  
    ::Platform::Collections::VectorViewIterator<T>   
    end(  
        IVectorView<T>^ v  
       );  
template <typename T>   
    ::Platform::Collections::InputIterator<T>   
    end(  
        IIterable<T>^ i  
       );  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Параметр типа шаблона.  
  
 `v`  
 Коллекция вектор\<T > или VectorView\<T > объекты, к которым подключены IVector\<T >, или IVectorView\<T > интерфейс.  
  
 `i`  
 Коллекция произвольных среды выполнения Windows объекты, которым осуществляется через IIterable\<T > интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, который указывает на позицию после конечного элемента коллекции.  
  
### <a name="remarks"></a>Примечания  
 Первые две функции шаблона возвращают итераторы, а третья возвращает итератор ввода.  
  
 Объект [Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md) , возвращаемый `end` , является итератором прокси-сервера, хранящего элементы типа `VectorProxy<T>`. Однако объект прокси-сервера практически никогда не отображается в пользовательском коде. Дополнительные сведения см. в разделе [Collections (C++/CX)](../cppcx/collections-c-cx.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Windows::Foundation::Collections  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Windows::Foundation:: Collections](../cppcx/windows-foundation-collections-namespace-c-cx.md)