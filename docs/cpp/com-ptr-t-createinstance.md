---
title: "_com_ptr_t::CreateInstance | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::CreateInstance
dev_langs:
- C++
helpviewer_keywords:
- CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
caps.latest.revision: 6
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
ms.openlocfilehash: 1c07f7366c76c96580fc989475bd7f5ea23a38fe
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="comptrtcreateinstance"></a>_com_ptr_t::CreateInstance
**Блок, относящийся только к системам Майкрософт**  
  
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
  
-   **CreateInstance (** `clsidString` **,**`dwClsContext`**)** создает новый экземпляр объекта, заданного строка Юникода, которая содержит либо выполняющегося **CLSID** (начиная с «**{**») или **ProgID**.        
  
-   **CreateInstance (** `clsidStringA` **,**`dwClsContext`**)** создает новый экземпляр объекта, заданного строку многобайтовых символов, которая содержит либо выполнение ** CLSID** (начиная с «**{**») или **ProgID**.       Вызовы [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), который предполагает, что строка имеет кодовую страницу ANSI, а не кодовую страницу OEM.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_ptr_t](../cpp/com-ptr-t-class.md)
