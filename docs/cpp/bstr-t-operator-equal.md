---
title: _bstr_t::operator = | Документация Майкрософт
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
ms.openlocfilehash: 43e28aa7d7b3682c45f4f8b7a94e990374d83b46
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944163"
---
# <a name="bstrtoperator-"></a>_bstr_t::operator =
**Блок, относящийся только к системам Microsoft**  
  
 Присваивает новое значение существующему объекту `_bstr_t`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
_bstr_t& operator=(const _bstr_t& s1) throw ( );  
_bstr_t& operator=(const char* s2);  
_bstr_t& operator=(const wchar_t* s3);  
_bstr_t& operator=(const _variant_t& var);  
```  
  
#### <a name="parameters"></a>Параметры  
 *s1*  
 Объект `_bstr_t`, который требуется присвоить существующему объекту `_bstr_t`.  
  
 *s2*  
 Многобайтовая строка, которую требуется присвоить существующему объекту `_bstr_t`.  
  
 *S3*  
 Строка Юникода, которую требуется присвоить существующему объекту `_bstr_t`.  
  
 *var*  
 Объект `_variant_t`, который требуется присвоить существующему объекту `_bstr_t`.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="example"></a>Пример  
 См. в разделе [_bstr_t::Assign](../cpp/bstr-t-assign.md) пример использования **оператор =**.  
  
## <a name="see-also"></a>См. также  
 [_bstr_t Class](../cpp/bstr-t-class.md)