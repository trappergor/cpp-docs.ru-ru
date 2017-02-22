---
title: "CMFCDesktopAlertWnd Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCDesktopAlertWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDesktopAlertWnd class"
ms.assetid: 73a2dd7b-ea84-4ae2-9830-7cf6e8dd2425
caps.latest.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 35
---
# CMFCDesktopAlertWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCDesktopAlertWnd` реализует функциональность немодального диалогового окна, кажется, что на экране сообщает пользователю о событии.  
  
## Синтаксис  
  
```  
class CMFCDesktopAlertWnd : public CWnd  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md)|Создает и инициализирует окно предупреждения.|  
|[CMFCDesktopAlertWnd::GetAnimationSpeed](../Topic/CMFCDesktopAlertWnd::GetAnimationSpeed.md)|Возвращает скорость анимации.|  
|[CMFCDesktopAlertWnd::GetAnimationType](../Topic/CMFCDesktopAlertWnd::GetAnimationType.md)|Возвращает тип анимации.|  
|[CMFCDesktopAlertWnd::GetAutoCloseTime](../Topic/CMFCDesktopAlertWnd::GetAutoCloseTime.md)|Возвращает время окончания ПУСТО.|  
|[CMFCDesktopAlertWnd::GetCaptionHeight](../Topic/CMFCDesktopAlertWnd::GetCaptionHeight.md)|Возвращает высоту заголовка.|  
|[CMFCDesktopAlertWnd::GetDialogSize](../Topic/CMFCDesktopAlertWnd::GetDialogSize.md)||  
|[CMFCDesktopAlertWnd::GetLastPos](../Topic/CMFCDesktopAlertWnd::GetLastPos.md)|Возвращает последнюю допустимую позицию окна оповещения на экране.|  
|[CMFCDesktopAlertWnd::GetTransparency](../Topic/CMFCDesktopAlertWnd::GetTransparency.md)|Возвращает уровень прозрачности.|  
|[CMFCDesktopAlertWnd::HasSmallCaption](../Topic/CMFCDesktopAlertWnd::HasSmallCaption.md)|Указывает, отображается ли окно предупреждения с небольшим заголовком.|  
|[CMFCDesktopAlertWnd::OnBeforeShow](../Topic/CMFCDesktopAlertWnd::OnBeforeShow.md)||  
|[CMFCDesktopAlertWnd::OnClickLinkButton](../Topic/CMFCDesktopAlertWnd::OnClickLinkButton.md)|Вызываемый платформой, когда пользователь нажимает кнопку, расположенную в меню связей рабочего стола оповещения.|  
|[CMFCDesktopAlertWnd::OnCommand](../Topic/CMFCDesktopAlertWnd::OnCommand.md)|Платформа вызывает функцию этот функцию\-член, когда пользователь выбирает элемент из меню, если дочерний элемент управления отправляет сообщение уведомления или если нажатие клавиши сочетаний клавиш преобразуется.  \(Переопределяет [CWnd::OnCommand](../Topic/CWnd::OnCommand.md)\).|  
|[CMFCDesktopAlertWnd::OnDraw](../Topic/CMFCDesktopAlertWnd::OnDraw.md)||  
|[CMFCDesktopAlertWnd::ProcessCommand](../Topic/CMFCDesktopAlertWnd::ProcessCommand.md)||  
|[CMFCDesktopAlertWnd::SetAnimationSpeed](../Topic/CMFCDesktopAlertWnd::SetAnimationSpeed.md)|Задает новую скорость анимации.|  
|[CMFCDesktopAlertWnd::SetAnimationType](../Topic/CMFCDesktopAlertWnd::SetAnimationType.md)|Задает тип анимации.|  
|[CMFCDesktopAlertWnd::SetAutoCloseTime](../Topic/CMFCDesktopAlertWnd::SetAutoCloseTime.md)|Задает время окончания ПУСТО.|  
|[CMFCDesktopAlertWnd::SetSmallCaption](../Topic/CMFCDesktopAlertWnd::SetSmallCaption.md)|Переключение между обычным небольших и заголовками.|  
|[CMFCDesktopAlertWnd::SetTransparency](../Topic/CMFCDesktopAlertWnd::SetTransparency.md)|Задает уровень непрозрачности.|  
  
## Заметки  
 Окно оповещения может быть явным образом, оно может находиться с эффектами анимации и может исчезнуть \(после заданной задержки, либо когда пользователь закрывает его, нажав кнопку "Закрыть"\).  
  
 Окно предупреждения также могут содержаться по умолчанию диалоговое окно, в свою очередь, содержит значок текст сообщения \(метки\), а также ссылка.  Кроме того, окно предупреждения может содержать пользовательское диалоговое окно из ресурсов приложения.  
  
 Создается окно предупреждения в шагах 2.  Во\-первых, вызовите конструктор для создания объекта `CMFCDesktopAlertWnd`.  Во\-вторых, вызовите функцию\-член [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md) для создания окна и вложить его к объекту `CMFCDesktopAlertWnd`.  
  
 Объект `CMFCDesktopAlertWnd` создается нерегламентированное диалоговое окно дочернего элемента, которое заполняет клиентскую область окна предупреждения.  Диалоговое окно содержит все элементы управления, которые расположены на него.  
  
 Для отображения настраиваемого диалогового окна во всплывающем окне, выполните следующие действия:  
  
1.  Наследование класса от класса `CMFCDesktopAlertDialog`.  
  
2.  Создание шаблона диалогового окна дочернего элемента в ресурсах.  
  
3.  Вызовите [CMFCDesktopAlertWnd::Create](../Topic/CMFCDesktopAlertWnd::Create.md) с помощью идентификатора ресурса шаблона диалоговых окон и указатель на данные среды выполнения класса, производного класса.  
  
4.  Запрограммируйте пользовательское диалоговое окно, чтобы обрабатывать все уведомления, поступающих из размещенного элемента управления или запрограммируйте размещенного элемента управления, чтобы обработать эти уведомления напрямую.  
  
 Следующие функции используются для мониторинга расширения функциональности окна предупреждения:  
  
-   Установите тип анимации, вызвав [CMFCDesktopAlertWnd::SetAnimationType](../Topic/CMFCDesktopAlertWnd::SetAnimationType.md).  Допустимые параметры: открытия, сползают и увядают.  
  
-   Установка скорости кадра анимации, вызвав [CMFCDesktopAlertWnd::SetAnimationSpeed](../Topic/CMFCDesktopAlertWnd::SetAnimationSpeed.md).  
  
-   Задание прозрачности уровня путем вызова [CMFCDesktopAlertWnd::SetTransparency](../Topic/CMFCDesktopAlertWnd::SetTransparency.md).  
  
-   Измените размер заголовка к малому путем вызова [CMFCDesktopAlertWnd::SetSmallCaption](../Topic/CMFCDesktopAlertWnd::SetSmallCaption.md).  Маленький заголовок 7 пикселей высокого уровня.  
  
## Пример  
 В следующем примере показано, как использовать различные методы в классе `CMFCDesktopAlertWnd` для настройки объект `CMFCDesktopAlertWnd`.  Примере показано, как задать тип анимации, установите уровень непрозрачности контекстного меню окна, указывающее, что окно предупреждения отображает маленький заголовок и укажите время, elapses перед бдительным окном автоматически закрыть.  В примере также показано, как создать и инициализировать окно предупреждения.  Этот фрагмент кода является частью [Пример demo рабочего стола предупреждений](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#1](../../mfc/reference/codesnippet/CPP/cmfcdesktopalertwnd-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)  
  
## Требования  
 **заголовок:** afxDesktopAlertWnd.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCDesktopAlertWndInfo Class](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)   
 [CMFCDesktopAlertDialog Class](../../mfc/reference/cmfcdesktopalertdialog-class.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)