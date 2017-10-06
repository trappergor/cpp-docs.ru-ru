---
title: "_variant_t::_variant_t | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::_variant_t
dev_langs:
- C++
helpviewer_keywords:
- _variant_t class, constructor
- _variant_t method
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
caps.latest.revision: 7
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
ms.openlocfilehash: 6bd29401970d3beffcac6d29247138aa65d6a338
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="varianttvariantt"></a>_variant_t::_variant_t
**Блок, относящийся только к системам Майкрософт**  
  
 Создает объект `_variant_t`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      _variant_t( ) throw( );  
  
_variant_t(  
   const VARIANT& varSrc   
);  
  
_variant_t(  
   const VARIANT* pVarSrc   
);  
  
_variant_t(  
   const _variant_t& var_t_Src   
);  
  
_variant_t(  
   VARIANT& varSrc,  
   bool fCopy   
);  
  
_variant_t(  
   short sSrc,  
   VARTYPE vtSrc = VT_I2   
);  
  
_variant_t(  
   long lSrc,  
   VARTYPE vtSrc = VT_I4   
);  
  
_variant_t(  
   float fltSrc   
) throw( );  
  
_variant_t(  
   double dblSrc,  
   VARTYPE vtSrc = VT_R8   
);  
  
_variant_t(  
   const CY& cySrc   
) throw( );  
  
_variant_t(  
   const _bstr_t& bstrSrc   
);  
  
_variant_t(  
   const wchar_t *wstrSrc   
);  
  
_variant_t(  
   const char* strSrc   
);  
  
_variant_t(  
   IDispatch* pDispSrc,  
   bool fAddRef = true   
) throw( );  
  
_variant_t(  
   bool bSrc   
) throw( );  
  
_variant_t(  
   IUnknown* pIUknownSrc,  
   bool fAddRef = true   
) throw( );  
  
_variant_t(  
   const DECIMAL& decSrc   
) throw( );  
  
_variant_t(  
   BYTE bSrc   
) throw( );  
  
variant_t(  
   char cSrc  
) throw();  
  
_variant_t(  
   unsigned short usSrc  
) throw();  
  
_variant_t(  
   unsigned long ulSrc  
) throw();  
  
_variant_t(  
   int iSrc  
) throw();  
  
_variant_t(  
   unsigned int uiSrc  
) throw();  
  
_variant_t(  
   __int64 i8Src  
) throw();  
  
_variant_t(  
   unsigned __int64 ui8Src  
) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *varSrc*  
 Объект **VARIANT** скопировать в новый объект `_variant_t` объекта.  
  
 *pVarSrc*  
 Указатель на **VARIANT** скопировать в новый объект `_variant_t` объекта.  
  
 *var_t_Src*  
 Объект `_variant_t`, который необходимо скопировать в новый объект `_variant_t`.  
  
 `fCopy`  
 Если значение равно false, предоставленного **VARIANT** объект присоединен к новому `_variant_t` объект без создания копии путем **VariantCopy**.  
  
 *Код sSrc*  
 Целочисленное значение, которое необходимо скопировать в новый объект `_variant_t`.  
  
 `vtSrc`  
 **VARTYPE** для нового `_variant_t` объекта.  
  
 *fltSrc dblSrc*  
 Числовое значение, которое необходимо скопировать в новый объект `_variant_t`.  
  
 `cySrc`  
 Объект **CY** скопировать в новый объект `_variant_t` объекта.  
  
 `bstrSrc`  
 Объект `_bstr_t`, который необходимо скопировать в новый объект `_variant_t`.  
  
 *strSrc wstrSrc*  
 Строка, которую необходимо скопировать в новый объект `_variant_t`.  
  
 `bSrc`  
 Значение `bool`, которое необходимо скопировать в новый объект `_variant_t`.  
  
 `pIUknownSrc`  
 Указатель на интерфейс COM **VT_UNKNOWN** объект, который необходимо инкапсулировать в новый `_variant_t` объекта.  
  
 `pDispSrc`  
 Указатель на интерфейс COM **VT_DISPATCH** объект, который необходимо инкапсулировать в новый `_variant_t` объекта.  
  
 `decSrc`  
 Объект **ДЕСЯТИЧНОЕ** значения, которое копируется в новый `_variant_t` объекта.  
  
 `bSrc`  
 Объект **БАЙТОВ** значения, которое копируется в новый `_variant_t` объекта.  
  
 `cSrc`  
 Значение `char`, которое необходимо скопировать в новый объект `_variant_t`.  
  
 *usSrc*  
 Объект **short без знака** значения, которое копируется в новый `_variant_t` объекта.  
  
 *ulSrc*  
 Значение `unsigned long`, которое необходимо скопировать в новый объект `_variant_t`.  
  
 `iSrc`  
 Значение `int`, которое необходимо скопировать в новый объект `_variant_t`.  
  
 *uiSrc*  
 Значение `unsigned int`, которое необходимо скопировать в новый объект `_variant_t`.  
  
 *i8Src*  
 __**Int64** значения, которое копируется в новый `_variant_t` объекта.  
  
 *ui8Src*  
 **Unsigned __int64** значения, которое копируется в новый `_variant_t` объекта.  
  
## <a name="remarks"></a>Примечания  
  
-   **_variant_t ()** создает пустой `_variant_t` объекта, `VT_EMPTY`.  
  
-   **_variant_t (VARIANT &***varSrc***)** создает `_variant_t` объекта из копии **VARIANT** объекта.     Тип variant сохранен.  
  
-   **_variant_t (VARIANT\****pVarSrc***)** создает `_variant_t` объекта из копии **VARIANT** объекта.     Тип variant сохранен.  
  
-   **_variant_t (_variant_t &***var_t_Src***)** создает `_variant_t` объекта из другого `_variant_t` объекта.     Тип variant сохранен.  
  
-   **_variant_t (VARIANT &***varSrc* **, bool**`fCopy`**)** создает `_variant_t` объекта из существующего ** VARIANT** объекта.       Если `fCopy` — **false**, **VARIANT** объект присоединен к новому объекту без создания копии.  
  
-   **_variant_t (короткое***sSrc* **, VARTYPE**`vtSrc`**= VT_I2)** создает `_variant_t` объекта типа `VT_I2` или `VT_BOOL` из **короткие** целочисленное значение.       Любой другой **VARTYPE** приводит к `E_INVALIDARG` ошибки.  
  
-   **_variant_t (long** `lSrc` **, VARTYPE**`vtSrc`**= VT_I4)** создает `_variant_t` объекта типа `VT_I4`, `VT_BOOL`, или `VT_ERROR` из **длинные** целочисленное значение.       Любой другой **VARTYPE** приводит к `E_INVALIDARG` ошибки.  
  
-   **_variant_t (float**`fltSrc`**)** создает `_variant_t` объекта типа `VT_R4` из **float** числовое значение.      
  
-   **_variant_t (double** `dblSrc` **, VARTYPE**`vtSrc`**= VT_R8)** создает `_variant_t` объекта типа `VT_R8` или `VT_DATE` из **двойные** числовое значение.       Любой другой **VARTYPE** приводит к `E_INVALIDARG` ошибки.  
  
-   **_variant_t (CY &**`cySrc`**)** создает `_variant_t` объекта типа `VT_CY` из **CY** объекта.      
  
-   **_variant_t (_bstr_t &**`bstrSrc`**)** создает `_variant_t` объекта типа `VT_BSTR` из `_bstr_t` объекта.     Выделяется новый параметр `BSTR`.  
  
-   **_variant_t (wchar_t \* ** *wstrSrc***)** создает `_variant_t` объекта типа `VT_BSTR` строки Юникода.   Выделяется новый параметр `BSTR`.  
  
-   **_variant_t (char\***`strSrc`**)** создает `_variant_t` объекта типа `VT_BSTR` из строки.     Выделяется новый параметр `BSTR`.  
  
-   **_variant_t (bool**`bSrc`**)** создает `_variant_t` объекта типа `VT_BOOL` из `bool` значение.      
  
-   **_variant_t (IUnknown\* ** `pIUknownSrc` **, bool**`fAddRef`**= true)** создает `_variant_t` объекта типа **VT_UNKNOWN ** из указателя интерфейса СОМ.       Если `fAddRef` — **true**, затем `AddRef` вызывается в предоставленном указателе на интерфейс для соответствия вызову **выпуска** , который выполняется при `_variant_t` объект удаляется. Можно вызвать **выпуска** в предоставленном указателе на интерфейс. Если `fAddRef` — **false**, этот конструктор принимает право на владение предоставленным указателем на интерфейс, не следует вызывать **выпуска** в предоставленном указателе на интерфейс.  
  
-   **_variant_t (IDispatch\* ** `pDispSrc` **, bool**`fAddRef`**= true)** создает `_variant_t` объекта типа **VT_DISPATCH ** из указателя интерфейса СОМ.       Если `fAddRef` — **true**, затем `AddRef` вызывается в предоставленном указателе на интерфейс для соответствия вызову **выпуска** , который выполняется при `_variant_t` объект удаляется. Можно вызвать **выпуска** в предоставленном указателе на интерфейс. Если **fAddRef** имеет значение false, этот конструктор принимает право на владение предоставленным указателем на интерфейс, не следует вызывать **выпуска** в предоставленном указателе на интерфейс.  
  
-   **_variant_t (ДЕСЯТИЧНОЕ &**`decSrc`**)** создает `_variant_t` объекта типа **VT_DECIMAL** из **ДЕСЯТИЧНОЕ** значение.      
  
-   **_variant_t (BYTE**`bSrc`**)** создает `_variant_t` объекта типа `VT_UI1` из **БАЙТОВ** значение.      
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _variant_t](../cpp/variant-t-class.md)
