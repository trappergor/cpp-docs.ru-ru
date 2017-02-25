---
title: "CMDIChildWnd Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMDIChildWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "дочерние окна, CMDIChildWnd class"
  - "CMDIChildWnd class"
  - "MDI [C++], дочерние окна"
  - "windows [C++], MDI - интерфейс"
ms.assetid: 6d07f5d4-9a3e-4723-9fa5-e65bb669fdd5
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMDIChildWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональность дочернего окна документа Windows с несколькими интерфейса \(MDI\) вместе с элементами управления в окне.  
  
## Синтаксис  
  
```  
class CMDIChildWnd : public CFrameWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMDIChildWnd::CMDIChildWnd](../Topic/CMDIChildWnd::CMDIChildWnd.md)|Создает объект `CMDIChildWnd`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMDIChildWnd::Create](../Topic/CMDIChildWnd::Create.md)|Создает дочернее окно MDI Windows, связанное с объектом `CMDIChildWnd`.|  
|[CMDIChildWnd::GetMDIFrame](../Topic/CMDIChildWnd::GetMDIFrame.md)|Возвращает родительский кадр MDI окна клиента MDI.|  
|[CMDIChildWnd::MDIActivate](../Topic/CMDIChildWnd::MDIActivate.md)|Активировать это дочернее окно MDI.|  
|[CMDIChildWnd::MDIDestroy](../Topic/CMDIChildWnd::MDIDestroy.md)|Уничтожает это дочернее окно MDI.|  
|[CMDIChildWnd::MDIMaximize](../Topic/CMDIChildWnd::MDIMaximize.md)|Развернуть это дочернее окно MDI.|  
|[CMDIChildWnd::MDIRestore](../Topic/CMDIChildWnd::MDIRestore.md)|Извлекает это дочернее окно MDI из развернутого или свернутого размера.|  
|[CMDIChildWnd::SetHandles](../Topic/CMDIChildWnd::SetHandles.md)|Задает маркеры для ресурсов меню и сочетаний клавиш.|  
  
## Заметки  
 Дочернее окно MDI выглядит аналогично типичное фреймовое окно, за исключением того, что дочернее окно MDI появляется внутри фреймового окна MDI, а не на рабочем столе.  Дочернее окно MDI не содержит строку меню его вместо этого он использует фреймового окна меню MDI.  Платформа автоматически изменяются меню кадра MDI, чтобы представлять активное в данный момент дочернее окно MDI.  
  
 Чтобы создать полезный дочернее окно MDI для конкретного приложения, создайте класс, наследуемый от `CMDIChildWnd`.  Добавьте элемент переменные к производному классу для хранения данных, относящийся к приложению.  Реализуйте функции\-члены обработчика сообщений и сопоставление сообщения в производном классе позволяет определить, что происходит, когда сообщения направляются в окно.  
  
 3 Способа построения дочернее окно MDI:  
  
-   Непосредственно постройте его с помощью **Создать**.  
  
-   Непосредственно постройте его с помощью `LoadFrame`.  
  
-   Косвенно выполните его построение с помощью шаблона документа.  
  
 Прежде чем вызывать метод **Создать** или `LoadFrame` необходимо построить объекте фреймового окна в куче с помощью оператора C\+\+ **новый**.  Перед вызовом **Создать** можно также зарегистрировать класс окна с функцией [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) глобальный, чтобы задать стили значка и класса для кадра.  
  
 Использование функции\-члена **Создать** чтобы передать параметры создания кадра, как непосредственные аргументы.  
  
 `LoadFrame` требуется меньшее число аргументов, чем **Создать**, а вместо этого извлекает большинство значений по умолчанию из ресурсов, включая заголовок кадра, значок таблицы сочетаний клавиш и меню.  `LoadFrame` быть доступны все эти ресурсы должны иметь один и тот же идентификатор ресурсов \(например, **IDR\_MAINFRAME**\).  
  
 Если объект `CMDIChildWnd` содержащий представления и документов, они созданы неявно платформой, а не напрямую по программиста.  Объект `CDocTemplate` оркеструет создание фрейма, создание представлений и представлений, содержащий соединение в соответствующий документу.  Параметры конструктора `CDocTemplate` определяют `CRuntimeClass` 3 классов, которые участвуют \(документ, кадр и представление\).  Объект `CRuntimeClass` используется платформой для динамического создания новых определенный пользователем кадров \(например, с помощью команды файла новой или команды в окне интерфейса MDI новую\).  
  
 Класс фреймового окна, производный от `CMDIChildWnd` должен быть объявлен с `DECLARE_DYNCREATE`, вышеуказанный механизм `RUNTIME_CLASS` работал правильно.  
  
 Класс `CMDIChildWnd` наследует большую часть своей реализации по умолчанию из `CFrameWnd`.  Подробный список этих функций см. в описании класса [CFrameWnd](../../mfc/reference/cframewnd-class.md).  Класс `CMDIChildWnd`, имеет следующие дополнительные функции:  
  
-   Совместно с классом `CMultiDocTemplate`, несколько объектов `CMDIChildWnd` из одного шаблона документа используют один и тот же меню, при сохранении ресурсы системы Windows.  
  
-   Активное в данный момент меню дочернего окна MDI полностью заменяет фреймового окна меню MDI и заголовок активное в данный момент дочернее окно MDI добавлено к заголовку фреймового окна MDI.  Другие примеры функций дочернего окна MDI, предоставляемые вместе с фреймовым окно MDI см. в описании класса `CMDIFrameWnd`.  
  
 Не используйте оператор C\+\+ **удалить** для уничтожения фреймовое окно.  Взамен рекомендуется использовать `CWnd::DestroyWindow`.  Реализация `CFrameWnd``PostNcDestroy` удаляет объект C\+\+, если окно будет удалено.  Когда пользователь закрывает фреймовое окно, по умолчанию будут вызывать `DestroyWindow` обработчика `OnClose`.  
  
 Дополнительные сведения о `CMDIChildWnd` см. в разделе [фреймовые окна](../../mfc/frame-windows.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIChildWnd`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [MFC, пытается интерфейс MDI](../../top/visual-cpp-samples.md)   
 [Образец MDIDOCVW MFC](../../top/visual-cpp-samples.md)   
 [Образец SNAPVW MFC](../../top/visual-cpp-samples.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [CMDIFrameWnd Class](../../mfc/reference/cmdiframewnd-class.md)