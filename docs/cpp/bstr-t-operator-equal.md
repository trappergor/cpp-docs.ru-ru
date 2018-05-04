---
title: _bstr_t::operator = | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator = [C++], bstr
- operator= [C++], bstr
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e5537f4ad3abbac9686272e15d06bfa5df0bfca6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="bstrtoperator-"></a>_bstr_t::operator =
**Блок, относящийся только к системам Microsoft**  
  
 Присваивает новое значение существующему объекту `_bstr_t`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      _bstr_t& operator=(  
   const _bstr_t& s1   
) throw ( );  
_bstr_t& operator=(  
   const char* s2   
);  
_bstr_t& operator=(  
   const wchar_t* s3   
);  
_bstr_t& operator=(  
   const _variant_t& var   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *S1*  
 Объект `_bstr_t`, который требуется присвоить существующему объекту `_bstr_t`.  
  
 *S2*  
 Многобайтовая строка, которую требуется присвоить существующему объекту `_bstr_t`.  
  
 `s3`  
 Строка Юникода, которую требуется присвоить существующему объекту `_bstr_t`.  
  
 `var`  
 Объект `_variant_t`, который требуется присвоить существующему объекту `_bstr_t`.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="example"></a>Пример  
 В разделе [_bstr_t::Assign](../cpp/bstr-t-assign.md) пример использования `operator=`.  
  
## <a name="see-also"></a>См. также  
 [_bstr_t Class](../cpp/bstr-t-class.md)