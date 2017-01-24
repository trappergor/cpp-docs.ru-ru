---
title: "_com_ptr_t::CreateInstance | Microsoft Docs"
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
  - "_com_ptr_t::CreateInstance"
  - "_com_ptr_t.CreateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateInstance - метод"
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_ptr_t::CreateInstance
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Создает новый экземпляр объекта, учитывая **CLSID** или **ProgID**.  
  
## Синтаксис  
  
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
  
#### Параметры  
 `rclsid`  
 **CLSID** объекта.  
  
 `clsidString`  
 Строка Юникода, которая содержит либо **CLSID** \(начинается с символа "**{**"\), либо **ProgID**.  
  
 `clsidStringA`  
 Многобайтовая строка с кодовой страницей ANSI, которая содержит либо **CLSID** \(начинается с символа "**{**"\), либо **ProgID**.  
  
 `dwClsContext`  
 Контекст для выполняющегося исполняемого кода.  
  
 `pOuter`  
 Внешняя неизвестная строка для [агрегирования](../atl/aggregation.md).  
  
## Заметки  
 Эти функции\-члены вызывают `CoCreateInstance` для создания нового COM\-объект, а затем запрашивают тип интерфейса данного интеллектуального указателя.  Результирующий указатель затем инкапсулируется в этот объект `_com_ptr_t`.  Метод **Release** вызывается для уменьшения числа ссылок для ранее инкапсулированного указателя.  Эта процедура возвращает значение `HRESULT`, которое указывает успешность или сбой выполнения.  
  
-   **CreateInstance\(**  `rclsid` **,**  `dwClsContext`  **\)** Создает новый выполняемый экземпляр объекта, учитывая **CLSID**.  
  
-   **CreateInstance\(**  `clsidString` **,**  `dwClsContext`  **\)** Создает новый выполняемый экземпляр объекта, учитывая строку Юникода, содержащую **CLSID** \(начиная с "**{**"\) или **ProgID**.  
  
-   **CreateInstance\(**  `clsidStringA` **,**  `dwClsContext`  **\)** Создает новый выполняемый экземпляр объекта, учитывая строку многобайтовых символов, содержащую **CLSID** \(начиная с "**{**"\) или **ProgID**.  Вызывает метод [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), который предполагает, что строка имеет кодовую страницу ANSI, а не кодовую страницу OEM.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_com\_ptr\_t](../cpp/com-ptr-t-class.md)