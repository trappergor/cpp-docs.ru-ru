---
title: _com_ptr_t::CreateInstance | Документы Microsoft
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
ms.openlocfilehash: 70ccd73980295bdda67a4c49d034b6d185d2d93c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="comptrtcreateinstance"></a>_com_ptr_t::CreateInstance
**Блок, относящийся только к системам Microsoft**  
  
 Создает новый экземпляр объекта, заданного **CLSID** или **ProgID**.  
  
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
 `rclsid`  
 **CLSID** объекта.  
  
 `clsidString`  
 Строка Юникода, которая содержит либо **CLSID** (начиная с «**{**») или **ProgID**.  
  
 `clsidStringA`  
 Многобайтовая строка с кодовой страницей ANSI, которая содержит либо **CLSID** (начиная с «**{**») или **ProgID**.  
  
 `dwClsContext`  
 Контекст для выполняющегося исполняемого кода.  
  
 `pOuter`  
 Внешняя Неизвестная строка для [статистической обработки](../atl/aggregation.md).  
  
## <a name="remarks"></a>Примечания  
 Эти функции-члены вызывают `CoCreateInstance` для создания нового COM-объект, а затем запрашивают тип интерфейса данного интеллектуального указателя. Результирующий указатель затем инкапсулируется в этот объект `_com_ptr_t`. **Выпуск** вызывается для уменьшения числа ссылок для ранее инкапсулированного указателя. Эта процедура возвращает значение `HRESULT`, которое указывает успешность или сбой выполнения.  
  
-   **CreateInstance (** `rclsid` **,**`dwClsContext`**)** создает новый экземпляр объекта, заданного выполняющегося **CLSID**.        
  
-   **CreateInstance (** `clsidString` **,**`dwClsContext`**)** создает новый экземпляр объекта, заданного строка Юникода, которая содержит либо выполняющегося **CLSID**(начиная с «**{**») или **ProgID**.        
  
-   **CreateInstance (** `clsidStringA` **,**`dwClsContext`**)** создает новый экземпляр объекта, заданного строку многобайтовых символов, которая содержит либо выполняющегося **CLSID**  (начиная с «**{**») или **ProgID**.       Вызовы [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), который предполагает, что строка имеет кодовую страницу ANSI, а не кодовую страницу OEM.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_ptr_t](../cpp/com-ptr-t-class.md)