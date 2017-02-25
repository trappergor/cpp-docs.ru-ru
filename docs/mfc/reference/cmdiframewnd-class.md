---
title: "CMDIFrameWnd Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMDIFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMDIFrameWnd class"
  - "MDI frame windows"
ms.assetid: fa8736e6-511b-4c51-8b4d-eba78378aeb9
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMDIFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональность фреймового окна документа Windows с несколькими интерфейса \(MDI\) вместе с элементами управления в окне.  
  
## Синтаксис  
  
```  
class CMDIFrameWnd : public CFrameWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMDIFrameWnd::CMDIFrameWnd](../Topic/CMDIFrameWnd::CMDIFrameWnd.md)|Конструирует `CMDIFrameWnd`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMDIFrameWnd::CreateClient](../Topic/CMDIFrameWnd::CreateClient.md)|Создает окно Windows **MDICLIENT** для этого `CMDIFrameWnd`.  Вызванный функцией\-членом `OnCreate``CWnd`.|  
|[CMDIFrameWnd::CreateNewChild](../Topic/CMDIFrameWnd::CreateNewChild.md)|Создает новое дочернее окно.|  
|[CMDIFrameWnd::GetWindowMenuPopup](../Topic/CMDIFrameWnd::GetWindowMenuPopup.md)|Возвращает контекстное меню меню окно.|  
|[CMDIFrameWnd::MDIActivate](../Topic/CMDIFrameWnd::MDIActivate.md)|Активировать другое дочернее окно MDI.|  
|[CMDIFrameWnd::MDICascade](../Topic/CMDIFrameWnd::MDICascade.md)|Упорядочивает дочерние окна в каскадированном формате.|  
|[CMDIFrameWnd::MDIGetActive](../Topic/CMDIFrameWnd::MDIGetActive.md)|Возвращает активное в данный момент дочернее окно MDI, вместе с флагом, указывающий развернуть ли дочерний элемент.|  
|[CMDIFrameWnd::MDIIconArrange](../Topic/CMDIFrameWnd::MDIIconArrange.md)|Свернутые упорядочивает все дочерние окна документа.|  
|[CMDIFrameWnd::MDIMaximize](../Topic/CMDIFrameWnd::MDIMaximize.md)|Разверните дочернее окно MDI.|  
|[CMDIFrameWnd::MDINext](../Topic/CMDIFrameWnd::MDINext.md)|Активировать дочернее окно сразу за активное в данный момент дочернее окно и задает в настоящий момент активным окном за дочерним любых других дочерних окон.|  
|[CMDIFrameWnd::MDIPrev](../Topic/CMDIFrameWnd::MDIPrev.md)|Активировать предыдущее дочернее окно и устанавливает активное в данный момент дочернее окно немедленно за ним.|  
|[CMDIFrameWnd::MDIRestore](../Topic/CMDIFrameWnd::MDIRestore.md)|Возвращает дочернее окно MDI из развернутого или свернутого размера.|  
|[CMDIFrameWnd::MDISetMenu](../Topic/CMDIFrameWnd::MDISetMenu.md)|Заменяет фреймового окна меню MDI, раскрывающегося меню окна или и того, и другого.|  
|[CMDIFrameWnd::MDITile](../Topic/CMDIFrameWnd::MDITile.md)|Упорядочивает дочерние окна в замосщенном формате.|  
  
## Заметки  
 Чтобы создать полезный фреймовое окно MDI для конкретного приложения, создайте класс, наследуемый от `CMDIFrameWnd`.  Добавьте элемент переменные к производному классу для хранения данных, относящийся к приложению.  Реализуйте функции\-члены обработчика сообщений и сопоставление сообщения в производном классе позволяет определить, что происходит, когда сообщения направляются в окно.  
  
 Можно создавать фреймовое окно MDI путем вызова функции\-члена [Создание](../Topic/CFrameWnd::Create.md) или [LoadFrame](../Topic/CFrameWnd::LoadFrame.md)`CFrameWnd`.  
  
 Прежде чем вызывать метод **Создать** или `LoadFrame` необходимо построить объекте фреймового окна в куче с помощью оператора C\+\+ **новый**.  Перед вызовом **Создать** можно также зарегистрировать класс окна с функцией [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) глобальный, чтобы задать стили значка и класса для кадра.  
  
 Использование функции\-члена **Создать** чтобы передать параметры создания кадра, как непосредственные аргументы.  
  
 `LoadFrame` требуется меньшее число аргументов, чем **Создать**, а вместо этого извлекает большинство значений по умолчанию из ресурсов, включая заголовок кадра, значок таблицы сочетаний клавиш и меню.  К которым `LoadFrame`, все эти ресурсы должны иметь один и тот же идентификатор ресурсов \(например, **IDR\_MAINFRAME**\).  
  
 Хотя **MDIFrameWnd** является производным от `CFrameWnd`, классу фреймового окна, унаследованный от `CMDIFrameWnd` не должны быть объявлены с `DECLARE_DYNCREATE`.  
  
 Класс `CMDIFrameWnd` наследует большую часть своей реализации по умолчанию из `CFrameWnd`.  Подробный список этих функций см. в описании класса [CFrameWnd](../../mfc/reference/cframewnd-class.md).  Класс `CMDIFrameWnd`, имеет следующие дополнительные функции:  
  
-   Фреймовое окно MDI управляет окно **MDICLIENT**, проходящих его вместе с панелями элементов управления.  Окно клиента MDI непосредственно родительским фреймовых окон дочернего элемента интерфейса MDI.  Стили окна **WS\_HSCROLL** и **WS\_VSCROLL**, определенные в `CMDIFrameWnd` применяются к окну клиента MDI, а не основным фреймовое окно поэтому пользователь может прокручиваться клиентскую область MDI \(например, в Windows, например руководителе программ\).  
  
-   Фреймовое окно MDI содержит по умолчанию меню, которое используется в виде строки меню, если активное дочернее окно MDI.  Если активным является дочерним элементом MDI, строка меню MDI фреймового окна автоматически заменена меню дочернего окна MDI.  
  
-   Фреймовое окно MDI работает совместно с текущим дочерним окно MDI, если он имеется.  Например, сообщения команды делегированы для текущего активного дочернему элементу MDI перед фреймовым окно MDI.  
  
-   Фреймовое окно MDI содержит обработчики по умолчанию для следующих стандартных команд меню окна:  
  
    -   **ID\_WINDOW\_TILE\_VERT**  
  
    -   **ID\_WINDOW\_TILE\_HORZ**  
  
    -   **ID\_WINDOW\_CASCADE**  
  
    -   **ID\_WINDOW\_ARRANGE**  
  
-   Фреймовое окно MDI также содержит реализацию **ID\_WINDOW\_NEW**, которая создает новые кадр и представление в текущем документе.  Приложение может переопределить эти реализации по умолчанию команды для настройки обработки в окне интерфейса MDI.  
  
 Не используйте оператор C\+\+ **удалить** для уничтожения фреймовое окно.  Взамен рекомендуется использовать `CWnd::DestroyWindow`.  Реализация `CFrameWnd``PostNcDestroy` удаляет объект C\+\+, если окно будет удалено.  Когда пользователь закрывает фреймовое окно, по умолчанию будут вызывать `DestroyWindow` обработчика `OnClose`.  
  
 Дополнительные сведения о `CMDIFrameWnd` см. в разделе [фреймовые окна](../../mfc/frame-windows.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIFrameWnd`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [MFC, пытается интерфейс MDI](../../top/visual-cpp-samples.md)   
 [Образец MDIDOCVW MFC](../../top/visual-cpp-samples.md)   
 [Образец SNAPVW MFC](../../top/visual-cpp-samples.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [CMDIChildWnd Class](../../mfc/reference/cmdichildwnd-class.md)