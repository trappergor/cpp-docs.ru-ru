---
title: "CKeyboardManager Class | Microsoft Docs"
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
  - "CKeyboardManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CKeyboardManager class"
ms.assetid: 4809ece6-89df-4479-8b53-9bf476ee107b
caps.latest.revision: 33
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CKeyboardManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Таблицы сочетаний клавиш элементов управления для основных окон фреймовых фреймового окна и дочернего элемента.  
  
## Синтаксис  
  
```  
class CKeyboardManager : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CKeyboardManager::CKeyboardManager](../Topic/CKeyboardManager::CKeyboardManager.md)|Создает объект `CKeyboardManager`.|  
  
### Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CKeyboardManager::CleanUp](../Topic/CKeyboardManager::CleanUp.md)|Очищает таблицы сочетаний клавиш.|  
|[CKeyboardManager::FindDefaultAccelerator](../Topic/CKeyboardManager::FindDefaultAccelerator.md)|Извлекает по умолчанию сочетания клавиш для заданных команд и окна.|  
|[CKeyboardManager::IsKeyHandled](../Topic/CKeyboardManager::IsKeyHandled.md)|Определяет, является ли отрегулирован ключ таблицы сочетаний клавиш.|  
|[CKeyboardManager::IsKeyPrintable](../Topic/CKeyboardManager::IsKeyPrintable.md)|Указывает, является ли знак печати.|  
|[CKeyboardManager::IsShowAllAccelerators](../Topic/CKeyboardManager::IsShowAllAccelerators.md)|Указывает, отображаются ли все сочетания клавиш для команд меню или только по умолчанию сочетаний клавиш.|  
|[CKeyboardManager::LoadState](../Topic/CKeyboardManager::LoadState.md)|Загружает таблицы сочетаний клавиш из реестра Windows.|  
|[CKeyboardManager::ResetAll](../Topic/CKeyboardManager::ResetAll.md)|Перезапускает таблицы сочетаний клавиш из ресурса приложения.|  
|[CKeyboardManager::SaveState](../Topic/CKeyboardManager::SaveState.md)|Сохраняет таблицы сочетаний клавиш в реестр Windows.|  
|[CKeyboardManager::ShowAllAccelerators](../Topic/CKeyboardManager::ShowAllAccelerators.md)|Указывает, отображаются ли границы все сочетания клавиш для всех команд или одно сочетание клавиш для каждой команды.  Этот метод не влияет на команды, которые имеют только одно сочетание клавиш, связанное.|  
|[CKeyboardManager::TranslateCharToUpper](../Topic/CKeyboardManager::TranslateCharToUpper.md)|Преобразование символов в верхний регистр.|  
|[CKeyboardManager::UpdateAccelTable](../Topic/CKeyboardManager::UpdateAccelTable.md)|Обновляет таблицу сочетаний клавиш в новой таблице сочетаний клавиш.|  
  
## Заметки  
 Члены этого класса служат для сохранения и загрузки таблицы сочетаний клавиш в реестр Windows, использовать шаблон для обновления таблицы ключа сокращения и поиск по умолчанию сочетание клавиш для команд в фреймовом окне.  Кроме того, объект `CKeyboardManager` позволяет контролировать, как сочетание клавиш отображаются пользователю.  
  
 Не следует создать объект `CKeyboardManager` вручную.  Он будет создать автоматически платформой приложения.  Однако необходимо вызвать [CWinAppEx::InitKeyboardManager](../Topic/CWinAppEx::InitKeyboardManager.md) в процессе инициализации приложения.  Получить указатель на него клавиатуры для приложения, вызов [CWinAppEx::GetKeyboardManager](../Topic/CWinAppEx::GetKeyboardManager.md).  
  
## Пример  
 В следующем примере показано, как получить указатель на объект `CKeyboardManager` от класса `CWinAppEx` и отобразить все сочетания клавиш, связанные с командами меню.  Этот фрагмент кода является частью [Пользовательский образец страниц](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages#5](../../mfc/reference/codesnippet/CPP/ckeyboardmanager-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)  
  
## Требования  
 **заголовок:** afxkeyboardmanager.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [CWinAppEx::InitKeyboardManager](../Topic/CWinAppEx::InitKeyboardManager.md)   
 [Настройка мыши и клавиатуры](../../mfc/keyboard-and-mouse-customization.md)