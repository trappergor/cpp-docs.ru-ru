---
title: _variant_t::_variant_t | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::_variant_t
dev_langs:
- C++
helpviewer_keywords:
- _variant_t class [C++], constructor
- _variant_t method [C++]
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 95b0931438afe8ff151d3c9f6c4727013df79478
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209346"
---
# <a name="varianttvariantt"></a>_variant_t::_variant_t
**Блок, относящийся только к системам Microsoft**  
  
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
 Объект `VARIANT`, который необходимо скопировать в новый объект `_variant_t`.  
  
 *pVarSrc*  
 Указатель на `VARIANT` объект, который необходимо скопировать в новый `_variant_t` объекта.  
  
 *var_t_Src*  
 Объект `_variant_t`, который необходимо скопировать в новый объект `_variant_t`.  
  
 *fCopy*  
 Если **false**, предоставленного `VARIANT` объект присоединяется к новому `_variant_t` объект без создания новой копии с помощью `VariantCopy`.  
  
 *Код, sSrc*  
 Целочисленное значение, которое необходимо скопировать в новый объект `_variant_t`.  
  
 *vtSrc*  
 `VARTYPE` Для нового `_variant_t` объекта.  
  
 *fltSrc dblSrc*  
 Числовое значение, которое необходимо скопировать в новый объект `_variant_t`.  
  
 *cySrc*  
 Объект `CY`, который необходимо скопировать в новый объект `_variant_t`.  
  
 *bstrSrc*  
 Объект `_bstr_t`, который необходимо скопировать в новый объект `_variant_t`.  
  
 *strSrc wstrSrc*  
 Строка, которую необходимо скопировать в новый объект `_variant_t`.  
  
 *bSrc*  
 Объект **bool** значение для копирования в новый `_variant_t` объекта.  
  
 *pIUknownSrc*  
 Указатель на объект VT_UNKNOWN, который необходимо инкапсулировать в новый интерфейс COM `_variant_t` объекта.  
  
 *pDispSrc*  
 Указатель на объект VT_DISPATCH, который необходимо инкапсулировать в новый интерфейс COM `_variant_t` объекта.  
  
 *decSrc*  
 Значение `DECIMAL`, которое необходимо скопировать в новый объект `_variant_t`.  
  
 *bSrc*  
 Значение `BYTE`, которое необходимо скопировать в новый объект `_variant_t`.  
  
 *cSrc*  
 Объект **char** значение для копирования в новый `_variant_t` объекта.  
  
 *usSrc*  
 Объект **unsigned short** значение для копирования в новый `_variant_t` объекта.  
  
 *ulSrc*  
 Объект **unsigned long** значение для копирования в новый `_variant_t` объекта.  
  
 *Код*  
 **Int** значение для копирования в новый `_variant_t` объекта.  
  
 *uiSrc*  
 **Unsigned int** значение для копирования в новый `_variant_t` объекта.  
  
 *i8Src*  
 **__Int64** значение для копирования в новый `_variant_t` объекта.  
  
 *ui8Src*  
 **Unsigned __int64** значение для копирования в новый `_variant_t` объекта.  
  
## <a name="remarks"></a>Примечания  
  
-   **_variant_t ()** создает пустой `_variant_t` объекта, `VT_EMPTY`.  
  
-   **_variant_t (VARIANT &***varSrc***)** создает `_variant_t` объекта из копии `VARIANT` объекта.     Тип variant сохранен.  
  
-   **_variant_t (VARIANT**<strong>\*</strong>*pVarSrc***)** создает `_variant_t` объекта из копии `VARIANT` объекта.     Тип variant сохранен.  
  
-   **_variant_t (_variant_t &***var_t_Src***)** создает `_variant_t` из другого объекта `_variant_t` объекта.     Тип variant сохранен.  
  
-   **_variant_t (VARIANT &***varSrc* **, bool**`fCopy`**)** создает `_variant_t` из существующего `VARIANT` объект.       Если *fCopy* — **false**, **VARIANT** объект присоединен к новому объекту без создания копии.  
  
-   **_variant_t (короткий***sSrc* **, VARTYPE**`vtSrc`**= VT_I2)** создает `_variant_t` объект типа VT_I2 или VT_BOOL из **короткие** целочисленное значение.       Любой другой `VARTYPE` приводит к возникновению ошибки E_INVALIDARG.  
  
-   **_variant_t (long** `lSrc` **, VARTYPE**`vtSrc`**= VT_I4)** создает `_variant_t` объект типа VT_I4, VT_BOOL или VT_ERROR из **long**  целочисленное значение.       Любой другой `VARTYPE` приводит к возникновению ошибки E_INVALIDARG.  
  
-   **_variant_t (float**`fltSrc`**)** создает `_variant_t` объект типа VT_R4 из **float** числовое значение.      
  
-   **_variant_t (double** `dblSrc` **, VARTYPE**`vtSrc`**= VT_R8)** создает `_variant_t` тип VT_R8 или VT_DATE из объекта **двойной** числовое значение.       Любой другой `VARTYPE` приводит к возникновению ошибки E_INVALIDARG.  
  
-   **_variant_t (CY &**`cySrc`**)** создает `_variant_t` объект введите VT_CY из `CY` объекта.      
  
-   **_variant_t (_bstr_t &**`bstrSrc`**)** создает `_variant_t` объект типа VT_BSTR из `_bstr_t` объекта.     Выделяется новый параметр `BSTR`.  
  
-   **_variant_t (wchar_t** <strong>\*</strong> *wstrSrc***)** создает `_variant_t` объект типа VT_BSTR из строки Юникода.   Выделяется новый параметр `BSTR`.  
  
-   **_variant_t (char**<strong>\*</strong>`strSrc`**)** создает `_variant_t` объект типа VT_BSTR из строки.     Выделяется новый параметр `BSTR`.  
  
-   **_variant_t (bool**`bSrc`**)** создает `_variant_t` объект введите VT_BOOL из **bool** значение.      
  
-   **_variant_t (IUnknown** <strong>\*</strong> `pIUknownSrc` **, bool**`fAddRef`**= true)** создает `_variant_t` тип объекта VT_UNKNOWN из указателя интерфейса СОМ.       Если `fAddRef` — **true**, затем `AddRef` вызывается в предоставленном указателе на интерфейс для соответствия вызову `Release` , будет выполняться при `_variant_t` уничтожении объекта. Это следует вызвать метод `Release` в предоставленном указателе на интерфейс. Если `fAddRef` — **false**, этот конструктор принимает владение предоставленном указателе на интерфейс; не следует вызывать `Release` в предоставленном указателе на интерфейс.  
  
-   **_variant_t (IDispatch** <strong>\*</strong> `pDispSrc` **, bool**`fAddRef`**= true)** создает `_variant_t` объект Тип VT_DISPATCH из указателя интерфейса СОМ.       Если `fAddRef` — **true**, затем `AddRef` вызывается в предоставленном указателе на интерфейс для соответствия вызову `Release` , будет выполняться при `_variant_t` уничтожении объекта. Это следует вызвать метод `Release` в предоставленном указателе на интерфейс. Если `fAddRef` — **false**, этот конструктор принимает владение предоставленном указателе на интерфейс; не следует вызывать `Release` в предоставленном указателе на интерфейс.  
  
-   **_variant_t (DECIMAL &**`decSrc`**)** создает `_variant_t` объект введите VT_DECIMAL из `DECIMAL` значение.      
  
-   **_variant_t (BYTE**`bSrc`**)** создает `_variant_t` объект типа `VT_UI1` из `BYTE` значение.      
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _variant_t](../cpp/variant-t-class.md)