---
title: "CWinAppEx Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinAppEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinAppEx class"
ms.assetid: a3d3e053-3e22-463f-9444-c73abb1bb9d7
caps.latest.revision: 37
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 39
---
# CWinAppEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CWinAppEx` обрабатывает состояние приложения, сохраняет состояние в реестр загружает состояние из реестра, инициализирует диспетчеры приложения и приведены ссылки на те такие же диспетчеры приложения.  
  
## Синтаксис  
  
```  
class CWinAppEx : public CWinApp  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWinAppEx::CWinAppEx](../Topic/CWinAppEx::CWinAppEx.md)|Создает объект `CWinAppEx`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWinAppEx::CleanState](../Topic/CWinAppEx::CleanState.md)|Удаляет сведения о приложении из реестра Windows.|  
|[CWinAppEx::EnableLoadWindowPlacement](../Topic/CWinAppEx::EnableLoadWindowPlacement.md)|Указывает, загружает ли приложение исходные размер и местоположение главного фреймового окна из реестра.|  
|[CWinAppEx::EnableTearOffMenus](../Topic/CWinAppEx::EnableTearOffMenus.md)|Включает перемещаемые меню для приложения.|  
|[CWinAppEx::EnableUserTools](../Topic/CWinAppEx::EnableUserTools.md)|Позволяет пользователю создать пользовательские команды меню в приложении.|  
|[CWinAppEx::ExitInstance](../Topic/CWinAppEx::ExitInstance.md)|Вызываемый платформой функции\-члена из `Run` чтобы оставить этот экземпляр приложения.  \(Переопределяет [CWinApp::ExitInstance](../Topic/CWinApp::ExitInstance.md)\).|  
|[CWinAppEx::GetBinary](../Topic/CWinAppEx::GetBinary.md)|Считывает двоичные данные, которые сопоставлены с указанным значением реестра.|  
|[CWinAppEx::GetContextMenuManager](../Topic/CWinAppEx::GetContextMenuManager.md)|Возвращает указатель на глобальный объект [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).|  
|[CWinAppEx::GetDataVersion](../Topic/CWinAppEx::GetDataVersion.md)||  
|[CWinAppEx::GetDataVersionMajor](../Topic/CWinAppEx::GetDataVersionMajor.md)|Возвращает основной номер версии приложения, сохраненного в реестре Windows.|  
|[CWinAppEx::GetDataVersionMinor](../Topic/CWinAppEx::GetDataVersionMinor.md)|Возвращает дополнительный номер версии приложения, сохраненного в реестре Windows.|  
|[CWinAppEx::GetInt](../Topic/CWinAppEx::GetInt.md)|Считывает числовой тип данных, который связан с указанным значением из реестра.|  
|[CWinAppEx::GetKeyboardManager](../Topic/CWinAppEx::GetKeyboardManager.md)|Возвращает указатель на глобальный объект [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md).|  
|[CWinAppEx::GetMouseManager](../Topic/CWinAppEx::GetMouseManager.md)|Возвращает указатель на глобальный объект [CMouseManager](../../mfc/reference/cmousemanager-class.md).|  
|[CWinAppEx::GetObject](../Topic/CWinAppEx::GetObject.md)|Считывает `CObject`, унаследованных от данных, которые сопоставлены с заданным значением из реестра.|  
|[CWinAppEx::GetRegSectionPath](../Topic/CWinAppEx::GetRegSectionPath.md)|Возвращает строку, путь к разделу реестра.  Этот путь сцепляет предоставленный относительный путь с путем приложения.|  
|[CWinAppEx::GetRegistryBase](../Topic/CWinAppEx::GetRegistryBase.md)|Возвращает путь в реестре для приложения.|  
|[CWinAppEx::GetSectionBinary](../Topic/CWinAppEx::GetSectionBinary.md)|Считывает двоичные данные, которые сопоставлены с указанным ключом и значением из реестра.|  
|[CWinAppEx::GetSectionInt](../Topic/CWinAppEx::GetSectionInt.md)|Считывает числовые данные из реестра, связанного с указанным ключом и значением.|  
|[CWinAppEx::GetSectionObject](../Topic/CWinAppEx::GetSectionObject.md)|Считывает данные `CObject`, которые сопоставлены с указанным ключом и значением из реестра.|  
|[CWinAppEx::GetSectionString](../Topic/CWinAppEx::GetSectionString.md)|Считывает данные строки, которые сопоставлены с указанным ключом и значением из реестра.|  
|[CWinAppEx::GetShellManager](../Topic/CWinAppEx::GetShellManager.md)|Возвращает указатель на глобальный объект [CShellManager](../../mfc/reference/cshellmanager-class.md).|  
|[CWinAppEx::GetString](../Topic/CWinAppEx::GetString.md)|Считывает данные строки, которые сопоставлены с заданным значением из реестра.|  
|[CWinAppEx::GetTooltipManager](../Topic/CWinAppEx::GetTooltipManager.md)|Возвращает указатель на глобальный объект [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md).|  
|[CWinAppEx::GetUserToolsManager](../Topic/CWinAppEx::GetUserToolsManager.md)|Возвращает указатель на глобальный объект [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md).|  
|[CWinAppEx::InitContextMenuManager](../Topic/CWinAppEx::InitContextMenuManager.md)|Инициализирует объект `CContextMenuManager`.|  
|[CWinAppEx::InitKeyboardManager](../Topic/CWinAppEx::InitKeyboardManager.md)|Инициализирует объект `CKeyboardManager`.|  
|[CWinAppEx::InitMouseManager](../Topic/CWinAppEx::InitMouseManager.md)|Инициализирует объект `CMouseManager`.|  
|[CWinAppEx::InitShellManager](../Topic/CWinAppEx::InitShellManager.md)|Инициализирует класс `CShellManager`|  
|[CWinAppEx::InitTooltipManager](../Topic/CWinAppEx::InitTooltipManager.md)|Инициализирует класс `CTooltipManager`.|  
|[CWinAppEx::IsResourceSmartUpdate](../Topic/CWinAppEx::IsResourceSmartUpdate.md)||  
|[CWinAppEx::IsStateExists](../Topic/CWinAppEx::IsStateExists.md)|Указывает, является ли указанный ключ в реестре.|  
|[CWinAppEx::LoadState](../Topic/CWinAppEx::LoadState.md)|Загружает состояние приложения из реестра.|  
|[CWinAppEx::OnAppContextHelp](../Topic/CWinAppEx::OnAppContextHelp.md)|Вызываемый платформой, если справка контекста запросов пользователя для диалогового окна **Настройка**.|  
|[CWinAppEx::OnViewDoubleClick](../Topic/CWinAppEx::OnViewDoubleClick.md)|Вызывает определяемую пользователем команды, когда пользователь дважды щелкает мышью в любом месте приложения.|  
|[CWinAppEx::OnWorkspaceIdle](../Topic/CWinAppEx::OnWorkspaceIdle.md)||  
|[CWinAppEx::SaveState](../Topic/CWinAppEx::SaveState.md)|Записывает состояние платформы приложения в реестр Windows.|  
|[CWinAppEx::SetRegistryBase](../Topic/CWinAppEx::SetRegistryBase.md)|Задает путь по умолчанию раздела реестра.  Этот ключ будет служить корневой элемент для всех последующих вызовов реестра.|  
|[CWinAppEx::ShowPopupMenu](../Topic/CWinAppEx::ShowPopupMenu.md)|Отображает всплывающее меню.|  
|[CWinAppEx::WriteBinary](../Topic/CWinAppEx::WriteBinary.md)|Записывает двоичные данные равным заданному значению реестра.|  
|[CWinAppEx::WriteInt](../Topic/CWinAppEx::WriteInt.md)|Записывает числовые типы данных равным заданному значению реестра.|  
|[CWinAppEx::WriteObject](../Topic/CWinAppEx::WriteObject.md)|Записывает данные, полученные из [CObject Class](../Topic/CObject%20Class.md) равным заданному значению реестра.|  
|[CWinAppEx::WriteSectionBinary](../Topic/CWinAppEx::WriteSectionBinary.md)|Записывает двоичные данные в значение указанного раздела реестра.|  
|[CWinAppEx::WriteSectionInt](../Topic/CWinAppEx::WriteSectionInt.md)|Записывает числовые данные в значение указанного раздела реестра.|  
|[CWinAppEx::WriteSectionObject](../Topic/CWinAppEx::WriteSectionObject.md)|Записывает данные, производные от `CObject` классифицируют к значению указанного раздела реестра.|  
|[CWinAppEx::WriteSectionString](../Topic/CWinAppEx::WriteSectionString.md)|Записывает данные строки в значение указанного раздела реестра.|  
|[CWinAppEx::WriteString](../Topic/CWinAppEx::WriteString.md)|Записывает данные строки равным заданному значению реестра.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWinAppEx::LoadCustomState](../Topic/CWinAppEx::LoadCustomState.md)|Вызываемый платформой, когда состояние приложения будет загружен.|  
|[CWinAppEx::LoadWindowPlacement](../Topic/CWinAppEx::LoadWindowPlacement.md)|Вызываемый платформой, когда она нагрузят размер и расположение приложения из реестра.  Загруженные данные включают размер и местоположение главного фрейма в момент в закрытое последнее приложения.|  
|[CWinAppEx::OnClosingMainFrame](../Topic/CWinAppEx::OnClosingMainFrame.md)|Вызываемый платформой, когда основное фреймовое окно отображает `WM_CLOSE`.|  
|[CWinAppEx::PreLoadState](../Topic/CWinAppEx::PreLoadState.md)|Вызываемого инфраструктурой сразу после загрузки состояния приложения.|  
|[CWinAppEx::PreSaveState](../Topic/CWinAppEx::PreSaveState.md)|Вызываемого инфраструктурой сразу после того, как состояние приложения сохраняется.|  
|[CWinAppEx::ReloadWindowPlacement](../Topic/CWinAppEx::ReloadWindowPlacement.md)|Перезапускает размер и местоположение указанного окна из реестра|  
|[CWinAppEx::SaveCustomState](../Topic/CWinAppEx::SaveCustomState.md)|Вызываемый средой после того, как она записывает состояние приложения в реестр.|  
|[CWinAppEx::StoreWindowPlacement](../Topic/CWinAppEx::StoreWindowPlacement.md)|Вызываемый платформой для записи размер и местоположение главного фрейма в реестр.|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CWinAppEx::m\_bForceImageReset](../Topic/CWinAppEx::m_bForceImageReset.md)|Определяет, является ли сбросят границы всех изображений панели инструментов, когда фреймовое окно, которое содержит панель инструментов загружено.|  
  
## Заметки  
 Многие функции, предоставленные зависит от платформы MFC класс `CWinAppEx`.  Класс `CWinAppEx` можно включить в приложение в одном из 2 способов:  
  
-   Создайте класс `CWinAppEx` в основном потоке.  
  
-   Создайте класс главной программы из `CWinAppEx`.  
  
 После включения `CWinAppEx` в приложение можно инициализировать один из диспетчеров приложения.  Прежде чем использовать диспетчер приложения необходимо инициализировать его путем вызова соответствующего метода инициализации.  Для получения указателя на конкретный диспетчер, вызовите соответствующий метод get.  Класс `CWinAppEx` управляет следующих диспетчеров приложения: [CMouseManager Class](../../mfc/reference/cmousemanager-class.md), [CContextMenuManager Class](../../mfc/reference/ccontextmenumanager-class.md), [CKeyboardManager Class](../../mfc/reference/ckeyboardmanager-class.md), [CUserToolsManager Class](../../mfc/reference/cusertoolsmanager-class.md) и [CMenuTearOffManager Class](../../mfc/reference/cmenutearoffmanager-class.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 [CWinAppEx](../../mfc/reference/cwinappex-class.md)  
  
## Требования  
 **заголовок:** afxwinappex.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)   
 [CMouseManager Class](../../mfc/reference/cmousemanager-class.md)   
 [CContextMenuManager Class](../../mfc/reference/ccontextmenumanager-class.md)   
 [CKeyboardManager Class](../../mfc/reference/ckeyboardmanager-class.md)   
 [CUserToolsManager Class](../../mfc/reference/cusertoolsmanager-class.md)