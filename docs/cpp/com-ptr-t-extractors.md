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
ms.openlocfilehash: 31ac39104c041d1d119f6cd06de5f9c4a620dac0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190031"
---
# <a name="_com_ptr_t-extractors"></a>Средства извлечения _com_ptr_t

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

## <a name="remarks"></a>Remarks

- **интерфейс оператора** <strong>\*</strong> возвращает указатель инкапсулированного интерфейса, который может иметь значение null.

- **интерфейс оператора &** Возвращает ссылку на инкапсулированный указатель интерфейса и выдает ошибку, если указатель имеет значение NULL.

- **оператор** <strong>\*</strong> позволяет объекту интеллектуального указателя действовать так, как будто он был фактически инкапсулированным интерфейсом при разыменовании.

- **оператор->** Позволяет объекту интеллектуального указателя действовать так, будто он был фактически инкапсулированным интерфейсом при разыменовании.

- **оператор &** Освобождает любой инкапсулированный указатель интерфейса, заменяя его значением NULL, и возвращает адрес инкапсулированного указателя. Это позволяет передавать интеллектуальный указатель по адресу в функцию с параметром *out* , через который он возвращает указатель интерфейса.

- **bool, оператор** Позволяет использовать объект интеллектуального указателя в условном выражении. Этот оператор возвращает значение TRUE, если указатель не имеет значение NULL.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _com_ptr_t](../cpp/com-ptr-t-class.md)
