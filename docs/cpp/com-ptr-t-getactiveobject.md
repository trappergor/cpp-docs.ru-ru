---
title: _com_ptr_t::GetActiveObject | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::GetActiveObject
dev_langs:
- C++
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ccff761cb9b738de9e2f0debc470746d1482ab56
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940372"
---
# <a name="comptrtgetactiveobject"></a>_com_ptr_t::GetActiveObject
**Блок, относящийся только к системам Microsoft**  
  
 Присоединяет к существующему экземпляру объекта, учитывая `CLSID` или `ProgID`.  
  
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
 *rclsid*  
 `CLSID` Объекта.  
  
 *clsidString*  
 Строка Юникода, которая содержит либо `CLSID` (начиная с "**{**«) или `ProgID`.  
  
 *clsidStringA*  
 Многобайтовая строка, с помощью кодовой страницы ANSI, которая содержит либо `CLSID` (начиная с "**{**«) или `ProgID`.  
  
## <a name="remarks"></a>Примечания  
 Эти функции-члены вызывают функцию `GetActiveObject`, чтобы получить указатель на выполняющийся объект, который был зарегистрирован при помощи OLE, а затем запрашивает тип интерфейса этого интеллектуального указателя. Результирующий указатель затем инкапсулируется в этот объект `_com_ptr_t`. `Release` вызывается для уменьшения счетчика ссылок для ранее инкапсулированного указателя. Эта процедура возвращает значение HRESULT, указывающее успех или неудачу.  
  
-   **GetActiveObject (**`rclsid`**)** присоединяет к существующему экземпляру объекта, учитывая `CLSID`.      
  
-   **GetActiveObject (**`clsidString`**)** присоединяет к существующему экземпляру объекта, учитывая строку Юникода, которая содержит либо `CLSID` (начиная с "**{**«) или `ProgID`.      
  
-   **GetActiveObject (**`clsidStringA`**)** присоединяет к существующему экземпляру объекта, учитывая строку многобайтовых символов, которая содержит либо `CLSID` (начиная с "**{**«) или `ProgID`.     Вызовы [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), который предполагает, что строка имеет кодовую страницу ANSI, а не кодовую страницу OEM.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_ptr_t](../cpp/com-ptr-t-class.md)