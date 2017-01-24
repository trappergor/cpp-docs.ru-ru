---
title: "IAxWinHostWindowLic Interface | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IAxWinHostWindowLic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAxWinHostWindowLic interface"
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IAxWinHostWindowLic Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот интерфейс предоставляет методы для управления лицензированный элемент управления и его объект основного приложения.  
  
## Синтаксис  
  
```  
  
interface IAxWinHostWindowLic : IAxWinHostWindow  
  
```  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[CreateControlLic](../Topic/IAxWinHostWindowLic::CreateControlLic.md)|Создает вложение лицензированный элемент управления и его к объекту основного приложения.|  
|[CreateControlLicEx](../Topic/IAxWinHostWindowLic::CreateControlLicEx.md)|Создает лицензированный элемент управления, вложение его к объекту основного приложения, и при необходимости настраивает обработчик событий.|  
  
## Заметки  
 `IAxWinHostWindowLic` наследуется от [IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) и добавляет методы, поддерживающие создание лицензированных элементов управления.  
  
 См. раздел [Размещение элементов управления ActiveX с использованием библиотеки ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) пример, использующий элементы этого интерфейса.  
  
## Требования  
 Определение этого интерфейса доступен как IDL или C\+\+, как показано ниже.  
  
|Тип определения|Файл|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C\+\+|ATLIFace.h \(также включается в ATLBase.h\)|