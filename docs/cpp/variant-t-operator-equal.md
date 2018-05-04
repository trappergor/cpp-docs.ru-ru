---
title: _variant_t::operator = | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= [C++], variant
- operator = [C++], variant
- = operator [C++], with specific Visual C++ objects
ms.assetid: 77622723-6e49-4dec-9e0f-fa74028f1a3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0db0ea95fe3f5491780cd0297e8d3f56b6800e1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="varianttoperator-"></a>_variant_t::operator =
**Блок, относящийся только к системам Microsoft**  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      _variant_t& operator=(  
   const VARIANT& varSrc   
);  
  
_variant_t& operator=(  
   const VARIANT* pVarSrc   
);  
  
_variant_t& operator=(  
   const _variant_t& var_t_Src   
);  
  
_variant_t& operator=(  
   short sSrc   
);  
  
_variant_t& operator=(  
   long lSrc   
);  
  
_variant_t& operator=(  
   float fltSrc   
);  
  
_variant_t& operator=(  
   double dblSrc   
);  
  
_variant_t& operator=(  
   const CY& cySrc   
);  
  
_variant_t& operator=(  
   const _bstr_t& bstrSrc   
);  
  
_variant_t& operator=(  
   const wchar_t* wstrSrc   
);  
  
_variant_t& operator=(  
   const char* strSrc   
);  
  
_variant_t& operator=(  
   IDispatch* pDispSrc   
);  
  
_variant_t& operator=(  
   bool bSrc   
);  
  
_variant_t& operator=(  
   IUnknown* pSrc   
);  
  
_variant_t& operator=(  
   const DECIMAL& decSrc   
);  
  
_variant_t& operator=(  
   BYTE bSrc   
);  
  
_variant_t& operator=(  
   char cSrc  
);  
  
_variant_t& operator=(  
   unsigned short usSrc  
);  
  
_variant_t& operator=(  
   unsigned long ulSrc  
);  
  
_variant_t& operator=(  
   int iSrc  
);  
  
_variant_t& operator=(  
   unsigned int uiSrc  
);  
  
_variant_t& operator=(  
   __int64 i8Src  
);  
  
_variant_t& operator=(  
   unsigned __int64 ui8Src  
);  
```  
  
## <a name="remarks"></a>Примечания  
 Оператор присваивает новое значение объекту `_variant_t`.  
  
-   **оператор = (***varSrc***)** присваивает существующий **VARIANT** для `_variant_t` объекта.      
  
-   **оператор = (***pVarSrc***)** присваивает существующий **VARIANT** для `_variant_t` объекта.      
  
-   **оператор = (***var_t_Src***)** присваивает существующий `_variant_t` объект `_variant_t` объекта.      
  
-   **оператор = (***sSrc***)** назначает **короткие** целочисленное значение для `_variant_t` объекта.      
  
-   **оператор = (**`lSrc`**)** назначает **длинные** целочисленное значение для `_variant_t` объекта.      
  
-   **оператор = (***fltSrc***)** назначает **float** числовое значение, которое `_variant_t` объекта.      
  
-   **оператор = (***dblSrc***)** назначает **двойные** числовое значение, которое `_variant_t` объекта.      
  
-   **оператор = (***cySrc***)** назначает **CY** объект `_variant_t` объекта.      
  
-   **оператор = (***bstrSrc***)** назначает `BSTR` объект `_variant_t` объекта.      
  
-   **оператор = (***wstrSrc***)** назначает строку в Юникоде `_variant_t` объекта.      
  
-   **оператор = (**`strSrc`**)** назначает многобайтовой строки в `_variant_t` объекта.      
  
-   **оператор = (** `bSrc` **)** назначает `bool` значение `_variant_t` объекта.    
  
-   **оператор = (***pDispSrc***)** назначает **VT_DISPATCH** объект `_variant_t` объекта.      
  
-   **оператор = (***pIUnknownSrc***)** назначает **VT_UNKNOWN** объект `_variant_t` объекта.      
  
-   **оператор = (***decSrc***)** назначает **ДЕСЯТИЧНОЕ** значение `_variant_t` объекта.      
  
-   **оператор = (** `bSrc` **)** назначает **БАЙТОВ** значение `_variant_t` объекта.    
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _variant_t](../cpp/variant-t-class.md)