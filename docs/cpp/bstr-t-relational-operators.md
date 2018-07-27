---
title: Операторы отношения _bstr_t | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator>
- _bstr_t::operator==
- _bstr_t::operator>=
- _bstr_t::operator!=
- _bstr_t::operator<
- _bstr_t::operator<=
- _bstr_t::operator!
dev_langs:
- C++
helpviewer_keywords:
- '>= operator [C++], comparing specific objects'
- operator<= [C++], bstr
- '!= operator'
- operator == [C++], bstr
- operator!= [C++], relational operators
- < operator [C++], comparing specific objects
- relational operators [C++], _bstr_t class
- operator== [C++], bstr
- <= operator [C++], with specific objects
- operator <= [C++], bstr
- operator >= [C++], bstr
- operator != [C++], relational operators
- '> operator [C++], comparing specific objects'
- operator< [C++], bstr
- == operator [C++], with specific Visual C++ objects
- operator>= [C++], bstr
- operator < [C++], bstr
- operator > [C++], bstr
ms.assetid: e153da72-37c3-4d8a-b8eb-730d65da64dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 40834c7c41bc19b395958b4a173a68bd014b2e70
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944597"
---
# <a name="bstrt-relational-operators"></a>Операторы отношения _bstr_t
**Блок, относящийся только к системам Microsoft**  
  
 Сравнивает два объекта `_bstr_t`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
bool operator!( ) const throw( );   
bool operator==(const _bstr_t& str) const throw( );  
bool operator!=(const _bstr_t& str) const throw( );  
bool operator<(const _bstr_t& str) const throw( );  
bool operator>(const _bstr_t& str) const throw( );  
bool operator<=(const _bstr_t& str) const throw( );  
bool operator>=(const _bstr_t& str) const throw( );  
```  
  
## <a name="remarks"></a>Примечания  
 Эти операторы производят лексикографическое сравнение двух объектов `_bstr_t` . Операторы возвращают значение TRUE Если сравнение верно; в противном случае возвращает значение FALSE.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [_bstr_t Class](../cpp/bstr-t-class.md)