---
title: _com_ptr_t::CreateInstance | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::CreateInstance
dev_langs:
- C++
helpviewer_keywords:
- CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bde476af66ae0a5a560019db29d25385c718e517
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201806"
---
# <a name="comptrtcreateinstance"></a>_com_ptr_t::CreateInstance
**Блок, относящийся только к системам Microsoft**  
  
 Создает новый экземпляр объекта, учитывая `CLSID` или `ProgID`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateInstance(  
   const CLSID& rclsid,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
HRESULT CreateInstance(  
   LPCWSTR clsidString,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
HRESULT CreateInstance(  
   LPCSTR clsidStringA,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 *rclsid*  
 `CLSID` Объекта.  
  
 *clsidString*  
 Строка Юникода, которая содержит либо `CLSID` (начиная с "**{**«) или `ProgID`.  
  
 *clsidStringA*  
 Многобайтовая строка, с помощью кодовой страницы ANSI, которая содержит либо `CLSID` (начиная с "**{**«) или `ProgID`.  
  
 *dwClsContext*  
 Контекст для выполняющегося исполняемого кода.  
  
 *pOuter*  
 Внешняя Неизвестная строка для [статистической обработки](../atl/aggregation.md).  
  
## <a name="remarks"></a>Примечания  
 Эти функции-члены вызывают `CoCreateInstance` для создания нового COM-объект, а затем запрашивают тип интерфейса данного интеллектуального указателя. Результирующий указатель затем инкапсулируется в этот объект `_com_ptr_t`. `Release` вызывается для уменьшения счетчика ссылок для ранее инкапсулированного указателя. Эта процедура возвращает значение HRESULT, указывающее успех или неудачу.  
  
-   **CreateInstance (***rclsid* **,***dwClsContext***)** создает новый выполняемый экземпляр объекта, учитывая `CLSID`.  
  
-   **CreateInstance (***clsidString* **,***dwClsContext***)** создает новый выполняемый экземпляр объекта, учитывая Строка Юникода, которая содержит либо `CLSID` (начиная с "**{**«) или `ProgID`.  
  
-   **CreateInstance (***clsidStringA* **,***dwClsContext***)** создает новый выполняемый экземпляр объекта, учитывая строки многобайтовых символов, которая содержит либо `CLSID` (начиная с "**{**«) или `ProgID`. Вызовы [MultiByteToWideChar](/windows/desktop/api/stringapiset/nf-stringapiset-multibytetowidechar), который предполагает, что строка имеет кодовую страницу ANSI, а не кодовую страницу OEM.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_ptr_t](../cpp/com-ptr-t-class.md)