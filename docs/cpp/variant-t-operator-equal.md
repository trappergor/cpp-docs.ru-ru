---
title: "_variant_t::operator = | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t.operator="
  - "_variant_t::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "= - оператор, с конкретными объектами Visual C++"
  - "оператор =, вариант"
  - "operator=, вариант"
ms.assetid: 77622723-6e49-4dec-9e0f-fa74028f1a3c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _variant_t::operator =
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
## Синтаксис  
  
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
  
## Заметки  
 Оператор присваивает новое значение объекту `_variant_t`.  
  
-   **operator\=\(**  *varSrc*  **\)** Присвоение существующего значения **VARIANT** объекту `_variant_t`.  
  
-   **operator\=\(**  *pVarSrc*  **\)** Присвоение существующего **VARIANT** объекту `_variant_t`.  
  
-   **operator\=\(**  *var\_t\_Src*  **\)** Присвоение существующего объекта `_variant_t` объекту `_variant_t`.  
  
-   **operator\=\(**  *sSrc*  **\)** Присвоение целочисленного значения **short** объекту `_variant_t`.  
  
-   **operator\=\(**  `lSrc`  **\)** Присвоение целочисленного значения **long** объекту `_variant_t`.  
  
-   **operator\=\(**  *fltSrc*  **\)** Присвоение числового значения **float** объекту `_variant_t`.  
  
-   **operator\=\(**  *dblSrc*  **\)** Присвоение числового значения **double** объекту `_variant_t`.  
  
-   **operator\=\(**  *cySrc*  **\)** Присвоение объекта **CY** объекту `_variant_t`.  
  
-   **operator\=\(**  *bstrSrc*  **\)** Присвоение объекта `BSTR` объекту `_variant_t`.  
  
-   **operator\=\(**  *wstrSrc*  **\)** Присвоение строки Юникода объекту `_variant_t`.  
  
-   **operator\=\(**  `strSrc`  **\)** Присвоение многобайтовой строки объекту `_variant_t`.  
  
-   **operator\=\(**  `bSrc` **\)** Присвоение значения `bool` объекту `_variant_t`.  
  
-   **operator\=\(**  *pDispSrc*  **\)** Присвоение объекта **VT\_DISPATCH** объекту `_variant_t`.  
  
-   **operator\=\(**  *pIUnknownSrc*  **\)** Присвоение объекта **VT\_UNKNOWN** объекту `_variant_t`.  
  
-   **operator\=\(**  *decSrc*  **\)** Присвоение значения **DECIMAL** объекту `_variant_t`.  
  
-   **operator\=\(**  `bSrc` **\)** Присвоение значения **BYTE** объекту `_variant_t`.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_variant\_t](../cpp/variant-t-class.md)