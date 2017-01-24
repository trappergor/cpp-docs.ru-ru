---
title: "CSettingsStore Class | Microsoft Docs"
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
  - "CSettingsStore"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSettingsStore class"
ms.assetid: 0ea181de-a13e-4b29-b560-7c43838223ff
caps.latest.revision: 29
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSettingsStore Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает программу\-оболочку функций API Windows, предоставляя объект\- выполнение интерфейс, который используется для доступа к реестру.  
  
## Синтаксис  
  
```  
class CSettingsStore : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSettingsStore::CSettingsStore](../Topic/CSettingsStore::CSettingsStore.md)|Создает объект `CSettingsStore`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSettingsStore::Close](../Topic/CSettingsStore::Close.md)|Закрывает открыть раздел реестра.|  
|[CSettingsStore::CreateKey](../Topic/CSettingsStore::CreateKey.md)|Открывает указанную пару или создает ее, если она не существует.|  
|[CSettingsStore::DeleteKey](../Topic/CSettingsStore::DeleteKey.md)|Удаляет указанный ключ и все его дочерние элементы.|  
|[CSettingsStore::DeleteValue](../Topic/CSettingsStore::DeleteValue.md)|Удаляет заданное значение открытого ключа.|  
|[CSettingsStore::Open](../Topic/CSettingsStore::Open.md)|Открывается указанный ключ.|  
|[CSettingsStore::Read](../Topic/CSettingsStore::Read.md)|Извлекает данные для значения заданного ключа.|  
|[CSettingsStore::Write](../Topic/CSettingsStore::Write.md)|Записывает значение в реестре с открытым ключом.|  
  
## Заметки  
 Функции\-члены `CreateKey` и `Open` очень похожи.  Если раздел реестра уже существует, то `CreateKey` и функция `Open` таким же образом.  Однако если раздел реестра не существует, то `CreateKey` создает его тогда как `Open` возвращает значение ошибки.  
  
## Пример  
 В следующем примере показано, как использовать открыть и прочитать методы `CSettingsStore` классифицируют.  Этот фрагмент кода является частью [Пример demo всплывающей подсказки](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_ToolTipDemo#1](../../mfc/reference/codesnippet/CPP/csettingsstore-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CSettingsStore](../../mfc/reference/csettingsstore-class.md)  
  
## Требования  
 **заголовок:** afxsettingsstore.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)