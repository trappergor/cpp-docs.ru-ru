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
ms.openlocfilehash: c8aca9422c4798cd798d048ce42443c4f38bd170
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944465"
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
  
-   **CreateInstance (***clsidStringA* **,***dwClsContext***)** создает новый выполняемый экземпляр объекта, учитывая строки многобайтовых символов, которая содержит либо `CLSID` (начиная с "**{**«) или `ProgID`.       Вызовы [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), который предполагает, что строка имеет кодовую страницу ANSI, а не кодовую страницу OEM.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_ptr_t](../cpp/com-ptr-t-class.md)