---
title: begin - функция
ms.date: 01/22/2017
f1_keywords:
- collection/Windows::Foundation::Collections::begin
helpviewer_keywords:
- begin Function
ms.assetid: 5a44fb33-e247-49fd-b7a1-4a5b42e9e1e4
ms.openlocfilehash: 1b95e4d32321aadf7de65ecb25109fbecd9eb614
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258295"
---
# <a name="begin-function"></a>begin - функция

Возвращает итератор, указывающий на начало коллекции, для доступа к которой используется указанный параметр интерфейса.

## <a name="syntax"></a>Синтаксис

```

template <typename T>
    ::Platform::Collections::VectorIterator<T>
    begin(
          IVector<T>^ v         );

template <typename T>
    ::Platform::Collections::VectorViewIterator<T>
    begin(
          IVectorView<T>^ v
         );

template <typename T>
    ::Platform::Collections::InputIterator<T>
    begin(
          IIterable<T>^ i         );
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Параметр типа шаблона.

*v*<br/>
Коллекция вектор\<T > или VectorView\<T > объекты, к которым подключены IVector\<T > или IVectorView\<T > интерфейс.

*i*<br/>
Коллекция произвольных объектов среды выполнения Windows, к которым подключены IIterable\<T > интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Итератор, который указывает на начало коллекции.

### <a name="remarks"></a>Примечания

Первые две функции шаблона возвращают итераторы, а третья возвращает итератор ввода.

Объект VectorIterator, объект, который возвращается методом begin, является итератором прокси-сервера, хранящего элементы типа VectorProxy\<T >. Однако объект прокси-сервера практически никогда не отображается в пользовательском коде. Дополнительные сведения см. в разделе [Collections (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Windows::Foundation:: Collections

## <a name="see-also"></a>См. также

[Пространство имен Windows::Foundation::Collections](../cppcx/windows-foundation-collections-namespace-c-cx.md)
