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
- += operator [C++], appending strings
- + operator [C++], _bstr_t objects
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1ceeec1461b05b25d4bb0b42321cb9b3988ce4b0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="bstrtoperator--"></a>_bstr_t::operator +=, +
**Блок, относящийся только к системам Microsoft**  
  
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