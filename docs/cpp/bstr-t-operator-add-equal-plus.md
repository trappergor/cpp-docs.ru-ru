---
title: "_bstr_t::operator += + | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
dev_langs:
- C++
helpviewer_keywords:
- += operator, appending strings
- + operator, _bstr_t objects
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 0ba8936df56359523a76992866642521f899af69
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="bstrtoperator--"></a>_bstr_t::operator +=, +
**Блок, относящийся только к системам Майкрософт**  
  
 Добавляет символы в конец объекта `_bstr_t` или объединяет две строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      _bstr_t& operator+=(  
   const _bstr_t& s1   
);  
_bstr_t operator+(  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const char* s2,  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const wchar_t* s3,  
   const _bstr_t& s1   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *s1*  
 Объект `_bstr_t`.  
  
 *s2*  
 Многобайтовая строка.  
  
 `s3`  
 Строка Юникода.  
  
## <a name="remarks"></a>Примечания  
 Эти операторы выполняют объединение строк:  
  
-   **оператор += (***s1***)** добавляет символы в инкапсулированный `BSTR` из *s1* инкапсулированный этотобъектвконец`BSTR`.      
  
-   **оператор + (***s1***)** возврат нового `_bstr_t` , формируется путем присоединения этот объект `BSTR` с данными о *s1*.      
  
-   **оператор + (***s2***&#124;** *s1***)** возвращает новую `_bstr_t` , сформированном путем объединения многобайтовой строки *s2*, преобразованной в Юникод, с `BSTR` содержащийся в *s1*.          
  
-   **оператор + (** `s3` **,***s1***)** возвращает новую `_bstr_t` , формируется путем присоединения строки в Юникоде `s3` с `BSTR` , содержащийся в *s1*.        
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [_bstr_t Class](../cpp/bstr-t-class.md)
