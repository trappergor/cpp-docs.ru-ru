---
title: "CMFCToolBarsCustomizeDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolBarsCustomizeDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarsCustomizeDialog class"
ms.assetid: 78e2cddd-4f13-4097-afc3-1ad646a113f1
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# CMFCToolBarsCustomizeDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Безрежимное диалоговое окно табуляции \([CPropertySheet Class](../../mfc/reference/cpropertysheet-class.md)\), которое позволяет пользователю настраивать панели инструментов, меню и сочетаний клавиш, определяемые пользователем средств и визуальный стиль в приложении.  Как правило, пользователь получает доступ к **Настроить** это диалоговое окно, выбрав в меню **Сервис**.  
  
 Диалоговое окно **Настроить** имеет 6 вкладок. **Команды**, **Панели инструментов**, **Сервис**, **Клавиатура**, **Меню** и **Параметры**.  
  
## Синтаксис  
  
```  
class CMFCToolBarsCustomizeDialog : public CPropertySheet  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog](../Topic/CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog.md)|Создает объект `CMFCToolBarsCustomizeDialog`.|  
|`CMFCToolBarsCustomizeDialog::~CMFCToolBarsCustomizeDialog`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddButton](../Topic/CMFCToolBarsCustomizeDialog::AddButton.md)|Вставляет кнопку панели инструментов в список команд на странице **Команды**|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenu](../Topic/CMFCToolBarsCustomizeDialog::AddMenu.md)|Загружает меню из ресурсов и вызывает [CMFCToolBarsCustomizeDialog::AddMenuCommands](../Topic/CMFCToolBarsCustomizeDialog::AddMenuCommands.md) для добавления, что меню в список команд на странице **Команды**.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenuCommands](../Topic/CMFCToolBarsCustomizeDialog::AddMenuCommands.md)|Загружает меню из ресурсов и вызывает [CMFCToolBarsCustomizeDialog::AddMenuCommands](../Topic/CMFCToolBarsCustomizeDialog::AddMenuCommands.md) для добавления, что меню в список команд на странице **Команды**.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddToolBar](../Topic/CMFCToolBarsCustomizeDialog::AddToolBar.md)|Загружает панель инструментов из ресурсов.  Затем для каждой команды в меню вызывает метод [CMFCToolBarsCustomizeDialog::AddButton](../Topic/CMFCToolBarsCustomizeDialog::AddButton.md) для вставки кнопку в список команд на странице **Команды** в указанной категории.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::Create](../Topic/CMFCToolBarsCustomizeDialog::Create.md)|Отображает диалоговое окно **Настройка**.|  
|`CMFCToolBarsCustomizeDialog::EnableTools`|Зарезервировано для использования в будущем.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars](../Topic/CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars.md)|Позволяет включить или отключить создание новых панелей инструментов с помощью диалогового окна **Настроить**.|  
|[CMFCToolBarsCustomizeDialog::FillAllCommandsList](../Topic/CMFCToolBarsCustomizeDialog::FillAllCommandsList.md)|Заполняет предоставленный объект `CListBox` с командами в категории **Все команды**.|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](../Topic/CMFCToolBarsCustomizeDialog::FillCategoriesComboBox.md)|Заполняет предоставленный объект `CComboBox` с именем каждой категории команд в диалоговом окне **Настроить**.|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesListBox](../Topic/CMFCToolBarsCustomizeDialog::FillCategoriesListBox.md)|Заполняет предоставленный объект `CListBox` с именем каждой категории команд в диалоговом окне **Настроить**.|  
|[CMFCToolBarsCustomizeDialog::GetCommandName](../Topic/CMFCToolBarsCustomizeDialog::GetCommandName.md)|Извлекает имя, сопоставлено с заданным идентификатором команды|  
|[CMFCToolBarsCustomizeDialog::GetCountInCategory](../Topic/CMFCToolBarsCustomizeDialog::GetCountInCategory.md)|Получает число элементов в предоставленном списке, имеющих заданную текстовую подпись.|  
|[CMFCToolBarsCustomizeDialog::GetFlags](../Topic/CMFCToolBarsCustomizeDialog::GetFlags.md)|Извлекает набор флагов, которые влияют на поведение диалогового окна.|  
|`CMFCToolBarsCustomizeDialog::GetThisClass`|Используемый платформой для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), который связан с этим типом класса.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage](../Topic/CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage.md)|Запускает редактор изображений, чтобы пользователь мог настраивать значок кнопки панели инструментов или пункта меню.|  
|[CMFCToolBarsCustomizeDialog::OnInitDialog](../Topic/CMFCToolBarsCustomizeDialog::OnInitDialog.md)|Переопределяет, чтобы увеличить инициализации страницы свойств.  \(Переопределяет [CPropertySheet::OnInitDialog](../Topic/CPropertySheet::OnInitDialog.md)\).|  
|[CMFCToolBarsCustomizeDialog::PostNcDestroy](../Topic/CMFCToolBarsCustomizeDialog::PostNcDestroy.md)|Вызываемый средой после того, как окно будет удалено.  \(Переопределяет `CPropertySheet::PostNcDestroy`\).|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RemoveButton](../Topic/CMFCToolBarsCustomizeDialog::RemoveButton.md)|Удаляет кнопку с указанным идентификатором команды из указанной категории или из всех категорий.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RenameCategory](../Topic/CMFCToolBarsCustomizeDialog::RenameCategory.md)|Переименовывает категорию в списке категорий на вкладке **Команды**.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::ReplaceButton](../Topic/CMFCToolBarsCustomizeDialog::ReplaceButton.md)|Заменяет кнопку в списке команды на вкладке **Команды** с новым объектом кнопки панели инструментов.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::SetUserCategory](../Topic/CMFCToolBarsCustomizeDialog::SetUserCategory.md)|Добавляет категорию в список категорий, которые будут отображены на вкладке **Команды**.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::CheckToolsValidity](../Topic/CMFCToolBarsCustomizeDialog::CheckToolsValidity.md)|Вызываемый средой, чтобы определить, является ли список определенных пользователем средств допустимым.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAfterChangeTool](../Topic/CMFCToolBarsCustomizeDialog::OnAfterChangeTool.md)|Вызываемый платформой, когда свойства определяемого пользователем изменения средства.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAssignKey](../Topic/CMFCToolBarsCustomizeDialog::OnAssignKey.md)|Определяет, является ли указанное сочетание клавиш могут быть присвоены действии.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnBeforeChangeTool](../Topic/CMFCToolBarsCustomizeDialog::OnBeforeChangeTool.md)|Определяет, является ли определяемое пользователем это средство можно изменить.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnInitToolsPage](../Topic/CMFCToolBarsCustomizeDialog::OnInitToolsPage.md)|Вызываемый платформой, когда пользователь выбирает на вкладку **Сервис** запросе.|  
  
## Заметки  
 Для отображения диалогового окна **Настроить** создайте объект `CMFCToolBarsCustomizeDialog` и вызовите метод [CMFCToolBarsCustomizeDialog::Create](../Topic/CMFCToolBarsCustomizeDialog::Create.md).  
  
 Пока активно диалоговое окно **Настроить** приложение работает в нерегламентированном режиме, который ограничивает пользователя задач настройки.  
  
## Пример  
 В следующем примере показано, как использовать различные методы класса `CMFCToolBarsCustomizeDialog`.  Примере показано, как заменить кнопку панели инструментов в списке команд на странице **Команды**, чтобы включить создание новых панелей инструментов с помощью диалогового окна **Настроить** и отобразить диалоговое окно **Настройка**.  Этот фрагмент кода является частью [Пример demo IE](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo#4](../../mfc/reference/codesnippet/CPP/cmfctoolbarscustomizedialog-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCToolBarsCustomizeDialog](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)  
  
## Требования  
 **заголовок:** afxToolBarsCustomizeDialog.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CPropertySheet Class](../../mfc/reference/cpropertysheet-class.md)