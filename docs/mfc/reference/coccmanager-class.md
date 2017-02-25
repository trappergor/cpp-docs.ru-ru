---
title: "COccManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COccManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "контейнер для элементов ActiveX [C++], control site"
  - "CNoTrackObject class"
  - "COccManager class"
  - "пользовательские элементы управления [MFC], sites"
ms.assetid: 7d47aeed-d1ab-48e3-b4cf-d429718e370a
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# COccManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Управляет другие сайты пользовательского элемента управления; реализованный `COleControlContainer` и объектами `COleControlSite`.  
  
## Синтаксис  
  
```  
class COccManager : public CNoTrackObject  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COccManager::CreateContainer](../Topic/COccManager::CreateContainer.md)|Создает объект **COleContainer**.|  
|[COccManager::CreateDlgControls](../Topic/COccManager::CreateDlgControls.md)|Создает управления ActiveX, размещенный связанным объектом `COleContainer`.|  
|[COccManager::CreateSite](../Topic/COccManager::CreateSite.md)|Создает объект `COleClientSite`.|  
|[COccManager::GetDefBtnCode](../Topic/COccManager::GetDefBtnCode.md)|Извлекает код кнопку по умолчанию.|  
|[COccManager::IsDialogMessage](../Topic/COccManager::IsDialogMessage.md)|Указывает целевой объект диалогового окна сообщения.|  
|[COccManager::IsLabelControl](../Topic/COccManager::IsLabelControl.md)|Определяет, если элемент управления элемента управления "Метка".|  
|[COccManager::IsMatchingMnemonic](../Topic/COccManager::IsMatchingMnemonic.md)|Определяет, совпадает мнемонике мнемоника текущего элемента управления.|  
|[COccManager::OnEvent](../Topic/COccManager::OnEvent.md)|Пытается обработать определенное событие.|  
|[COccManager::PostCreateDialog](../Topic/COccManager::PostCreateDialog.md)|Освобождает ресурсы, выделенные во время создания диалогового окна.|  
|[COccManager::PreCreateDialog](../Topic/COccManager::PreCreateDialog.md)|Обрабатывает шаблон диалогового окна для элементов управления ActiveX.|  
|[COccManager::SetDefaultButton](../Topic/COccManager::SetDefaultButton.md)|Переключает состояние по умолчанию управления.|  
|[COccManager::SplitDialogTemplate](../Topic/COccManager::SplitDialogTemplate.md)|Разделяет все существующие элементы управления ActiveX от общих элементов управления в указанном шаблоне диалогового окна.|  
  
## Заметки  
 Базовый класс, **CNoTrackObject**\- недокументированный базовый класс \(находится в AFXTLS.H\).  Разработанные для использования платформы MFC, классы, производные от класса **CNoTrackObject** неподатны от обнаружения утечек памяти.  Не рекомендуется непосредственно наследуется от **CNoTrackObject**.  
  
## Иерархия наследования  
 `CNoTrackObject`  
  
 `COccManager`  
  
## Требования  
 **Header:** afxocc.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleControlSite Class](../../mfc/reference/colecontrolsite-class.md)   
 [COleControlContainer Class](../../mfc/reference/colecontrolcontainer-class.md)