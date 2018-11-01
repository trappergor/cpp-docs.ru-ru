---
title: Средства извлечения _com_ptr_t
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::operatorInterface&
- _com_ptr_t::operatorbool
- _com_ptr_t::operator->
- _com_ptr_t::operator*
helpviewer_keywords:
- operator Interface& [C++]
- '* operator [C++], with specific objects'
- operator& [C++]
- operator* [C++]
- -> operator [C++], with specific objects
- '& operator [C++], with specific objects'
- operator Interface* [C++]
- operator * [C++]
- operator->
- operator bool
- extractors, _com_ptr_t class
- extractors [C++]
ms.assetid: 194b9e0e-123c-49ff-a187-0a7fcd68145a
ms.openlocfilehash: 494507592222a7cd6334f2272c3a306e61e5d47f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545981"
---
# <a name="comptrt-extractors"></a>Средства извлечения _com_ptr_t

**Блок, относящийся только к системам Microsoft**

Извлекают инкапсулированный указатель на COM-интерфейс.

## <a name="syntax"></a>Синтаксис

```
operator Interface*( ) const throw( ); 
operator Interface&( ) const; 
Interface& operator*( ) const; 
Interface* operator->( ) const; 
Interface** operator&( ) throw( ); 
operator bool( ) const throw( );
```

## <a name="remarks"></a>Примечания

- **Оператор Interface** <strong>\*</strong> возвращает инкапсулированный указатель на интерфейс, который может быть равно NULL.

- **Оператор Interface &** возвращает ссылку на инкапсулированный указатель на интерфейс и выдает ошибку, если указатель имеет значение NULL.

- **оператор** <strong>\*</strong> позволяет объекту интеллектуального указателя функционировать как бы он сам является инкапсулированным интерфейсом при разыменовании.

- **operator ->** позволяет объекту интеллектуального указателя функционировать как бы он сам является инкапсулированным интерфейсом при разыменовании.

- **оператор &** освобождает любой инкапсулированный указатель на интерфейс, заменяя его значением NULL и возвращает адрес инкапсулированного указателя. Это позволяет использовать смарт-указатель можно передавать по адресу на функцию, которая имеет *out* параметра, через которую он возвращает указатель интерфейса.

- **Operator bool** позволяет объекту интеллектуального указателя для использования в условном выражении. Этот оператор возвращает значение TRUE, если указатель не равен NULL.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_ptr_t](../cpp/com-ptr-t-class.md)