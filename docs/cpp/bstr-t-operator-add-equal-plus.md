---
title: _bstr_t::operator += + | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e443b233e19f6cdc64d7d6021a9a9c078a4f327
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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
 *S1*  
 Объект `_bstr_t`.  
  
 *S2*  
 Многобайтовая строка.  
  
 `s3`  
 Строка Юникода.  
  
## <a name="remarks"></a>Примечания  
 Эти операторы выполняют объединение строк:  
  
-   **оператор += (***s1***)** добавляет символы в инкапсулированный `BSTR` из *s1* инкапсулированный этотобъектвконец`BSTR`.      
  
-   **оператор + (***s1***)** возврат нового `_bstr_t` , формируется путем присоединения этот объект `BSTR` с данными о *s1*.      
  
-   **оператор + (***s2***&#124;***s1***)** возвращает новую `_bstr_t` , сформированном путем объединения Многобайтовая строка *s2*, преобразованной в Юникод, с `BSTR` , содержащийся в *s1*.          
  
-   **оператор + (** `s3` **,***s1***)** возвращает новую `_bstr_t` , формируется путем присоединения строки в Юникоде `s3` с `BSTR` , содержащийся в *s1*.        
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [_bstr_t Class](../cpp/bstr-t-class.md)