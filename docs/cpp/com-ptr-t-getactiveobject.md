---
title: "_com_ptr_t::GetActiveObject | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::GetActiveObject
dev_langs:
- C++
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: a61e41c750fdf5865a475d92ba9e1def0aefd748
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="comptrtgetactiveobject"></a>_com_ptr_t::GetActiveObject
**Блок, относящийся только к системам Майкрософт**  
  
 Присоединяет к существующему экземпляру объекта, заданного **CLSID** или **ProgID**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT GetActiveObject(  
   const CLSID& rclsid   
) throw( );  
HRESULT GetActiveObject(  
   LPCWSTR clsidString   
) throw( );  
HRESULT GetActiveObject(  
   LPCSTR clsidStringA   
) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `rclsid`  
 **CLSID** объекта.  
  
 `clsidString`  
 Строка Юникода, которая содержит либо **CLSID** (начиная с «**{**») или **ProgID**.  
  
 `clsidStringA`  
 Многобайтовая строка с кодовой страницей ANSI, которая содержит либо **CLSID** (начиная с «**{**») или **ProgID**.  
  
## <a name="remarks"></a>Примечания  
 Эти функции-члены вызывают функцию `GetActiveObject`, чтобы получить указатель на выполняющийся объект, который был зарегистрирован при помощи OLE, а затем запрашивает тип интерфейса этого интеллектуального указателя. Результирующий указатель затем инкапсулируется в этот объект `_com_ptr_t`. **Выпуск** вызывается для уменьшения числа ссылок для ранее инкапсулированного указателя. Эта процедура возвращает значение `HRESULT`, которое указывает успешность или сбой выполнения.  
  
-   **GetActiveObject (**`rclsid`**)** присоединяет к существующему экземпляру объекта, заданного **CLSID**.      
  
-   **GetActiveObject (**`clsidString`**)** присоединяет к существующему экземпляру объекта, заданного строка Юникода, которая содержит либо **CLSID** (начиная с «**{**») или **ProgID**.      
  
-   **GetActiveObject (**`clsidStringA`**)** присоединяет к существующему экземпляру объекта, заданного строку многобайтовых символов, которая содержит либо **CLSID** (начиная с «**{**») или **ProgID**.     Вызовы [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), который предполагает, что строка имеет кодовую страницу ANSI, а не кодовую страницу OEM.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_ptr_t](../cpp/com-ptr-t-class.md)
