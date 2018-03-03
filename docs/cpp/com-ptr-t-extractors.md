---
title: "средства извлечения _com_ptr_t | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::operatorInterface&
- _com_ptr_t::operatorbool
- _com_ptr_t::operator->
- _com_ptr_t::operator*
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1c006c18b9e00e5c79ff686dfb31fa9ccf56fd4e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
  
-   **Оператор Interface\***  возвращает инкапсулированный указатель на интерфейс, который может быть **NULL**.  
  
-   **Оператор Interface &** возвращает ссылку на инкапсулированный указатель на интерфейс и выдает ошибку, если указатель находится **NULL**.  
  
-   **оператор\***  позволяет объекту интеллектуального указателя функционировать как если бы он сам является инкапсулированным интерфейсом при разыменовании.  
  
-   **operator ->** позволяет объекту интеллектуального указателя функционировать как если бы он сам является инкапсулированным интерфейсом при разыменовании.  
  
-   **оператор &** освобождает любой инкапсулированный указатель на интерфейс, заменяя его значением **NULL**и возвращает адрес инкапсулированного указателя. Это позволяет использовать смарт-указатель можно передавать по адресу функции, которая имеет **out** параметра, через которую он возвращает указатель на интерфейс.  
  
-   **Operator bool** позволяет объекту интеллектуального указателя для использования в условном выражении. Этот оператор возвращает **true** если указатель не имеет **NULL**.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_ptr_t](../cpp/com-ptr-t-class.md)