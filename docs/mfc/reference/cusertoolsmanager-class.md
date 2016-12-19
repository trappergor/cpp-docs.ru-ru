---
title: "CUserToolsManager Class | Microsoft Docs"
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
  - "CUserToolsManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUserToolsManager class"
ms.assetid: bdfa37ae-efca-4616-abb5-9d0dcd2d335b
caps.latest.revision: 26
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUserToolsManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Поддерживает коллекцию объектов [CUserTool Class](../Topic/CUserTool%20Class.md) в приложении.  Средство пользователя пункт меню, выполняемый внешнее приложение.  Объект `CUserToolsManager` позволяет пользователю или разработчик для добавления новых средств пользователя к приложению.  Он поддерживает выполнение команд, связанных со средствами пользователя, а также сохраняет сведения о средствах пользователя в реестре Windows.  
  
## Синтаксис  
  
```  
class CUserToolsManager : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CUserToolsManager::CUserToolsManager](../Topic/CUserToolsManager::CUserToolsManager.md)|Конструирует `CUserToolsManager`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CUserToolsManager::CreateNewTool](../Topic/CUserToolsManager::CreateNewTool.md)|Создает новое средство пользователя.|  
|[CUserToolsManager::FindTool](../Topic/CUserToolsManager::FindTool.md)|Возвращает указатель на объект `CMFCUserTool`, который связан с указанным идентификатором команды|  
|[CUserToolsManager::GetArgumentsMenuID](../Topic/CUserToolsManager::GetArgumentsMenuID.md)|Возвращает идентификатор ресурса, сопоставлено с меню **Аргументы** на вкладке **Сервис** диалогового окна **Настроить**.|  
|[CUserToolsManager::GetDefExt](../Topic/CUserToolsManager::GetDefExt.md)|Получает расширение по умолчанию, диалоговое окно **Открытие файла** \([CFileDialog::CFileDialog](../Topic/CFileDialog::CFileDialog.md)\) в поле **Команда** на вкладке **Сервис** диалогового окна **Настроить**.|  
|[CUserToolsManager::GetFilter](../Topic/CUserToolsManager::GetFilter.md)|Возвращает фильтр файлов, диалоговое окно **Открытие файла** \([CFileDialog Class](../Topic/CFileDialog%20Class.md)\) в поле **Команда** на вкладке **Сервис** диалогового окна **Настроить**.|  
|[CUserToolsManager::GetInitialDirMenuID](../Topic/CUserToolsManager::GetInitialDirMenuID.md)|Возвращает идентификатор ресурса, сопоставлено с меню **Исходный каталог** на вкладке **Сервис** диалогового окна **Настроить**.|  
|[CUserToolsManager::GetMaxTools](../Topic/CUserToolsManager::GetMaxTools.md)|Возвращает максимальное число средств пользователя, которые могут быть выбраны в приложении.|  
|[CUserToolsManager::GetToolsEntryCmd](../Topic/CUserToolsManager::GetToolsEntryCmd.md)|Возвращает идентификатор команды заполнителя пункта меню для средств пользователя.|  
|[CUserToolsManager::GetUserTools](../Topic/CUserToolsManager::GetUserTools.md)|Возвращает ссылку на список средств пользователя.|  
|[CUserToolsManager::InvokeTool](../Topic/CUserToolsManager::InvokeTool.md)|Выполняет приложение, связанное со средством пользователя, имеющего указанный идентификатор команды.|  
|[CUserToolsManager::IsUserToolCmd](../Topic/CUserToolsManager::IsUserToolCmd.md)|Определяет, является ли сопоставлено идентификатор команды с помощью инструмента пользователя.|  
|[CUserToolsManager::LoadState](../Topic/CUserToolsManager::LoadState.md)|Загружает сведения о средствах пользователя из реестра Windows.|  
|[CUserToolsManager::MoveToolDown](../Topic/CUserToolsManager::MoveToolDown.md)|Перемещает средство указанного пользователя вниз по списку средств пользователя.|  
|[CUserToolsManager::MoveToolUp](../Topic/CUserToolsManager::MoveToolUp.md)|Перемещает средство указанного пользователя вверх по списку средств пользователя.|  
|[CUserToolsManager::RemoveTool](../Topic/CUserToolsManager::RemoveTool.md)|Удаляет инструмент указанного пользователя из приложения.|  
|[CUserToolsManager::SaveState](../Topic/CUserToolsManager::SaveState.md)|Хранит сведения о средствах пользователя в реестре Windows.|  
|[CUserToolsManager::SetDefExt](../Topic/CUserToolsManager::SetDefExt.md)|Определяет расширение по умолчанию, диалоговое окно **Открытие файла** \([CFileDialog Class](../Topic/CFileDialog%20Class.md)\) в поле **Команда** на вкладке **Сервис** диалогового окна **Настроить**.|  
|[CUserToolsManager::SetFilter](../Topic/CUserToolsManager::SetFilter.md)|Задает фильтр файлов, диалоговое окно **Открытие файла** \([CFileDialog Class](../Topic/CFileDialog%20Class.md)\) в поле **Команда** на вкладке **Сервис** диалогового окна **Настроить**.|  
  
## Заметки  
 Включить средства пользователя в приложение.  
  
 1.  Зарезервируйте пункт меню и связанное идентификатор команды меню средства для записи пользователя.  
  
 2.  Зарезервируйте последовательное идентификатор команды для каждого средства пользователя, пользователь может определить в приложении.  
  
 3.  Вызовите метод [CWinAppEx::EnableUserTools](../Topic/CWinAppEx::EnableUserTools.md) и укажите следующие параметры: идентификатор команды меню, идентификатор команды средства первого пользователя и последнее идентификатор команды средства пользователя  
  
 Составление существует только один объект `CUserToolsManager` глобального в приложение.  
  
 Пример средств пользователя см. образец VisualStudioDemo проектов.  
  
## Пример  
 В следующем примере показано, как получить ссылку на объект `CUserToolsManager` и создании новых средств пользователя.  Этот фрагмент кода является частью [Пример demo Visual Studio](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#38](../../mfc/reference/codesnippet/CPP/cusertoolsmanager-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md)  
  
## Требования  
 **заголовок:** afxusertoolsmanager.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [CUserTool Class](../Topic/CUserTool%20Class.md)