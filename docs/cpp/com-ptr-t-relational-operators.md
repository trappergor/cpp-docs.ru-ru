---
title: Операторы отношения _com_ptr_t | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::operator>
- _com_ptr_t::operator>=
- _com_ptr_t::operator<=
- _com_ptr_t::operator==
- _com_ptr_t::operator!=
- _com_ptr_t::operator<
dev_langs:
- C++
helpviewer_keywords:
- '>= operator [C++], comparing specific objects'
- '!= operator'
- operator > [C++], pointers
- operator>= [C++], pointers
- operator < [C++], pointers
- operator!= [C++], relational operators
- < operator [C++], comparing specific objects
- operator== [C++], pointers
- operator == [C++], pointers
- <= operator [C++], with specific objects
- relational operators [C++], _com_ptr_t class
- operator >= [C++], pointers
- operator != [C++], relational operators
- operator <= [C++], pointers
- '> operator [C++], comparing specific objects'
- operator<= [C++], pointers
- operator< [C++], pointers
- == operator [C++], with specific Visual C++ objects
ms.assetid: 5ae4028c-33ee-485d-bbda-88d2604d6d4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6c338009b7dcd8f3810d48e17a4af470bee0837e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109318"
---
# <a name="comptrt-relational-operators"></a>Операторы отношения _com_ptr_t

**Блок, относящийся только к системам Microsoft**

Сравнение объекта интеллектуального указателя с другим интеллектуальным указателем, необработанным указателем на интерфейс, или значение NULL.

## <a name="syntax"></a>Синтаксис

```
template<typename _OtherIID> 
bool operator==( const _com_ptr_t<_OtherIID>& p );

template<typename _OtherIID>  
bool operator==( _com_ptr_t<_OtherIID>& p );

template<typename _InterfaceType> 
bool operator==( _InterfaceType* p );

template<> 
bool operator==( Interface* p );

template<> 
bool operator==( const _com_ptr_t& p ) throw();

template<> 
bool operator==( _com_ptr_t& p ) throw();

bool operator==( Int null );

template<typename _OtherIID> 
bool operator!=( const _com_ptr_t<_OtherIID>& p );

template<typename _OtherIID> 
bool operator!=( _com_ptr_t<_OtherIID>& p );

template<typename _InterfaceType> 
bool operator!=( _InterfaceType* p );

bool operator!=( Int null );

template<typename _OtherIID> 
bool operator<( const _com_ptr_t<_OtherIID>& p );

template<typename _OtherIID> 
bool operator<( _com_ptr_t<_OtherIID>& p );

template<typename _InterfaceType> 
bool operator<( _InterfaceType* p );

template<typename _OtherIID> 
bool operator>( const _com_ptr_t<_OtherIID>& p );

template<typename _OtherIID> 
bool operator>(_com_ptr_t< _OtherIID>& p );

template<typename _InterfaceType> 
bool operator>( _InterfaceType* p );

template<typename _OtherIID> 
bool operator<=( const _com_ptr_t<_OtherIID>& p );

template<typename _OtherIID> 
bool operator<=( _com_ptr_t<_OtherIID>& p );

template<typename _InterfaceType> 
bool operator<=( _InterfaceType* p );

template<typename _OtherIID>
bool operator>=( const _com_ptr_t<_OtherIID>& p );

template<typename _OtherIID> 
bool operator>=( _com_ptr_t<_OtherIID>& p );

template<typename _InterfaceType> 
bool operator>=( _InterfaceType* p );
```

## <a name="remarks"></a>Примечания

Сравнивает объект интеллектуального указателя в другой смарт-указателем, необработанным указателем на интерфейс, или значение NULL. За исключением тестов указателя NULL, эти операторы сначала запрашивают оба указателя для `IUnknown`и сравните результаты.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_ptr_t](../cpp/com-ptr-t-class.md)