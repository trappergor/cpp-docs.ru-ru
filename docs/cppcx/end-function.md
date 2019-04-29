---
title: Функция end
ms.date: 01/22/2017
f1_keywords:
- collection/Windows::Foundation::Collections::end
helpviewer_keywords:
- end Function
ms.assetid: fb837bff-fc76-4bae-9096-facf0e03041c
ms.openlocfilehash: c46c601be2b2ed78cf79641a7fcf5324e615a771
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375812"
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

*T*<br/>
Параметр типа шаблона.

*v*<br/>
Коллекция вектор\<T > или VectorView\<T > объекты, к которым подключены IVector\<T >, или IVectorView\<T > интерфейс.

*i*<br/>
Коллекция произвольных среды выполнения Windows объекты, которым осуществляется через IIterable\<T > интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Итератор, который указывает на позицию после конечного элемента коллекции.

### <a name="remarks"></a>Примечания

Первые две функции шаблона возвращают итераторы, а третья возвращает итератор ввода.

Объект [Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md) , возвращаемый `end` , является итератором прокси-сервера, хранящего элементы типа `VectorProxy<T>`. Однако объект прокси-сервера практически никогда не отображается в пользовательском коде. Дополнительные сведения см. в разделе [Collections (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Windows::Foundation:: Collections

## <a name="see-also"></a>См. также

[Пространство имен Windows::Foundation::Collections](../cppcx/windows-foundation-collections-namespace-c-cx.md)
