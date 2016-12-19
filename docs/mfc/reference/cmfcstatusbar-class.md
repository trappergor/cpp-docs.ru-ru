---
title: "CMFCStatusBar Class | Microsoft Docs"
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
  - "CMFCStatusBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCStatusBar class"
ms.assetid: f2960d1d-f4ed-41e8-bd99-0382b2f8d88e
caps.latest.revision: 36
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCStatusBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCStatusBar` реализует строку состояния, аналогичные классу `CStatusBar`.  Однако класс `CMFCStatusBar` имеет функции не предлагаемые классом `CStatusBar`, такие как возможность отображения образам, анимации и индикаторам выполнения; и возможность ответить на дважды щелкает мышью.  
  
## Синтаксис  
  
```  
class CMFCStatusBar : public CPane  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCStatusBar::CalcFixedLayout](../Topic/CMFCStatusBar::CalcFixedLayout.md)|\(Переопределяет [CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md)\).|  
|[CMFCStatusBar::CommandToIndex](../Topic/CMFCStatusBar::CommandToIndex.md)||  
|[CMFCStatusBar::Create](../Topic/CMFCStatusBar::Create.md)|Создает вложение панель элементов управления и его к объекту [CPane](../../mfc/reference/cpane-class.md).  \(Переопределяет [CPane::Create](../Topic/CPane::Create.md)\).|  
|[CMFCStatusBar::CreateEx](../Topic/CMFCStatusBar::CreateEx.md)|Создает вложение панель элементов управления и его к объекту [CPane](../../mfc/reference/cpane-class.md).  \(Переопределяет [CPane::CreateEx](../Topic/CPane::CreateEx.md)\).|  
|[CMFCStatusBar::DoesAllowDynInsertBefore](../Topic/CMFCStatusBar::DoesAllowDynInsertBefore.md)|Определяет, является ли другую панель можно динамически вставить между этой панелью и родительским кадром.  \(Переопределяет [CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md)\).|  
|[CMFCStatusBar::EnablePaneDoubleClick](../Topic/CMFCStatusBar::EnablePaneDoubleClick.md)|Включение или отключение обработка событий мыши дважды щелкает в строке состояния.|  
|[CMFCStatusBar::EnablePaneProgressBar](../Topic/CMFCStatusBar::EnablePaneProgressBar.md)|Отображает индикатор выполнения в определенной области.|  
|[CMFCStatusBar::GetCount](../Topic/CMFCStatusBar::GetCount.md)|Возвращает количество областей в строке состояния.|  
|[CMFCStatusBar::GetDrawExtendedArea](../Topic/CMFCStatusBar::GetDrawExtendedArea.md)||  
|[CMFCStatusBar::GetExtendedArea](../Topic/CMFCStatusBar::GetExtendedArea.md)||  
|[CMFCStatusBar::GetItemID](../Topic/CMFCStatusBar::GetItemID.md)||  
|[CMFCStatusBar::GetItemRect](../Topic/CMFCStatusBar::GetItemRect.md)||  
|[CMFCStatusBar::GetPaneInfo](../Topic/CMFCStatusBar::GetPaneInfo.md)||  
|[CMFCStatusBar::GetPaneProgress](../Topic/CMFCStatusBar::GetPaneProgress.md)||  
|[CMFCStatusBar::GetPaneStyle](../Topic/CMFCStatusBar::GetPaneStyle.md)|Возвращает стиль панели.  \(Переопределяет [CBasePane::GetPaneStyle](../Topic/CBasePane::GetPaneStyle.md)\).|  
|[CMFCStatusBar::GetPaneText](../Topic/CMFCStatusBar::GetPaneText.md)||  
|[CMFCStatusBar::GetPaneWidth](../Topic/CMFCStatusBar::GetPaneWidth.md)|Возвращает ширину в пикселях, указанную панели строки состояния.|  
|[CMFCStatusBar::GetTipText](../Topic/CMFCStatusBar::GetTipText.md)|Возвращает текст подсказки для указанной панели строки состояния.|  
|[CMFCStatusBar::InvalidatePaneContent](../Topic/CMFCStatusBar::InvalidatePaneContent.md)|Делает недействительной указанную область и перерисовывает его содержимое.|  
|[CMFCStatusBar::PreCreateWindow](../Topic/CMFCStatusBar::PreCreateWindow.md)|Вызывается инфраструктурой перед созданием окна Windows вложенного к данному объекту `CWnd`.  \(Переопределяет [CWnd::PreCreateWindow](../Topic/CWnd::PreCreateWindow.md)\).|  
|[CMFCStatusBar::SetDrawExtendedArea](../Topic/CMFCStatusBar::SetDrawExtendedArea.md)||  
|[CMFCStatusBar::SetIndicators](../Topic/CMFCStatusBar::SetIndicators.md)||  
|[CMFCStatusBar::SetPaneAnimation](../Topic/CMFCStatusBar::SetPaneAnimation.md)|Присвоит анимации к заданной области.|  
|[CMFCStatusBar::SetPaneBackgroundColor](../Topic/CMFCStatusBar::SetPaneBackgroundColor.md)|Устанавливает цвет фона для указанной панели строки состояния.|  
|[CMFCStatusBar::SetPaneIcon](../Topic/CMFCStatusBar::SetPaneIcon.md)|Задает значок индикатора для указанной панели строки состояния.|  
|[CMFCStatusBar::SetPaneInfo](../Topic/CMFCStatusBar::SetPaneInfo.md)||  
|[CMFCStatusBar::SetPaneProgress](../Topic/CMFCStatusBar::SetPaneProgress.md)|Задает текущий ход выполнения "Индикатор выполнения" для указанной панели строки состояния.|  
|[CMFCStatusBar::SetPaneStyle](../Topic/CMFCStatusBar::SetPaneStyle.md)|Задает стиль панели.  \(Переопределяет [CBasePane::SetPaneStyle](../Topic/CBasePane::SetPaneStyle.md)\).|  
|[CMFCStatusBar::SetPaneText](../Topic/CMFCStatusBar::SetPaneText.md)||  
|[CMFCStatusBar::SetPaneTextColor](../Topic/CMFCStatusBar::SetPaneTextColor.md)|Задает цвет текста для указанной панели строки состояния.|  
|[CMFCStatusBar::SetPaneWidth](../Topic/CMFCStatusBar::SetPaneWidth.md)|Задает ширину в пикселях, указанную панели строки состояния.|  
|[CMFCStatusBar::SetTipText](../Topic/CMFCStatusBar::SetTipText.md)|Задает текст всплывающей подсказки для указанной панели строки состояния.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCStatusBar::OnDrawPane](../Topic/CMFCStatusBar::OnDrawPane.md)|Вызываемый платформой, когда она перерисовывает панели строки состояния.|  
  
## Заметки  
 На следующей диаграмме показана диаграмма строки состояния из приложения [Пример demo строки состояния](../../top/visual-cpp-samples.md).  
  
 ![Пример CMFCStatusBar](../../mfc/reference/media/cmfcstatusbar.png "CMFCStatusBar")  
  
## Пример  
 В следующем примере демонстрируется локальные переменные, которые приложение использует для вызова различными методами класса `CMFCStatusBar`.  Эти переменные указываются в StatusBarDemoView.h.  Большая фрейма объявлена в документ, MainFrm.h объявлен в StatusBarDemoDoc.h и представление объявлено в StatusBarDemoView.h.  Этот фрагмент кода является частью [Пример demo строки состояния](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#9](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_1.h)]  
  
## Пример  
 В следующем примере показано, как получить ссылку на объект `CMFCStatusBar` путем вставки в метод `GetStatusBar` MainFrm.h а затем вызвать этот метод из метода `GetStatusBar` в StatusBarDemoView.h.  Этот фрагмент кода является частью [Пример demo строки состояния](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#7](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_2.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#8](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_3.h)]  
  
## Пример  
 В следующем примере показано, как вызывать различные методы в классе `CMFCStatusBar` в StatusBarDemoView.cpp.  Константы указываются в MainFrm.h.  Примере показано, как задать значок, установите текст подсказки панели строки состояния, отображает индикатор выполнения в определенной области присвоит анимации к заданной области, установите текста и ширины панели строки состояния и укажите текущий индикатор выполнения "Индикатор выполнения" для панели строки состояния.  Этот фрагмент кода является частью [Пример demo строки состояния](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#6](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_4.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#1](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_5.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#2](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_6.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#3](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_7.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#4](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_8.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#5](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_9.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)  
  
## Требования  
 **заголовок:** afxstatusbar.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CPane Class](../../mfc/reference/cpane-class.md)   
 [CStatusBar Class](../../mfc/reference/cstatusbar-class.md)