---
title: "Класс CMFCCaptionBar | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCCaptionBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс CMFCCaptionBar"
ms.assetid: acb54d5f-14ff-4c96-aeb3-7717cf566d9a
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# Класс CMFCCaptionBar
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Объект `CMFCCaptionBar` представляет панель элементов управления, может отображать 3 элемента: кнопка, метка текстовой подписи и растровое изображение.  Он может содержать только один элемент каждого типа одновременно.  Можно выравнивание каждый элемент в левого или правого краев элементов управления или к центру.  Также можно применить плоский или трехмерный стиль к верхним и нижним границам заголовка окна.  
  
## Синтаксис  
  
```  
class CMFCCaptionBar : public CPane  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCCaptionBar::Create](../Topic/CMFCCaptionBar::Create.md)|Создается элемент управления " заголовок окна " и вложение его в объект `CMFCCaptionBar`.|  
|[CMFCCaptionBar::DoesAllowDynInsertBefore](../Topic/CMFCCaptionBar::DoesAllowDynInsertBefore.md)|Указывает, является ли другой области можно динамически вставить между заголовком окна и его родительским кадром.  Переопределения \( [CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md)\).|  
|[CMFCCaptionBar::EnableButton](../Topic/CMFCCaptionBar::EnableButton.md)|Включает или отключит кнопки в заголовке окна.|  
|[CMFCCaptionBar::GetAlignment](../Topic/CMFCCaptionBar::GetAlignment.md)|Возвращает выравнивание указанного элемента.|  
|[CMFCCaptionBar::GetBorderSize](../Topic/CMFCCaptionBar::GetBorderSize.md)|Возвращает размер границы заголовка окна.|  
|[CMFCCaptionBar::GetButtonRect](../Topic/CMFCCaptionBar::GetButtonRect.md)|Возвращает ограничивающий прямоугольник кнопки в заголовке окна.|  
|[CMFCCaptionBar::GetMargin](../Topic/CMFCCaptionBar::GetMargin.md)|Возвращает расстояние между краем элемента управления и краем заголовка окна заголовка окна.|  
|[CMFCCaptionBar::IsMessageBarMode](../Topic/CMFCCaptionBar::IsMessageBarMode.md)|Определяет, является ли заголовок окна в режиме панели сообщений.|  
|[CMFCCaptionBar::RemoveBitmap](../Topic/CMFCCaptionBar::RemoveBitmap.md)|Удаляет образ растрового изображения из заголовка окна.|  
|[CMFCCaptionBar::RemoveButton](../Topic/CMFCCaptionBar::RemoveButton.md)|Удаляет из кнопки заголовка окна.|  
|[CMFCCaptionBar::RemoveIcon](../Topic/CMFCCaptionBar::RemoveIcon.md)|Удаляет Значок из заголовка окна.|  
|[CMFCCaptionBar::RemoveText](../Topic/CMFCCaptionBar::RemoveText.md)|Удаляет текстовая подпись из заголовка окна.|  
|[CMFCCaptionBar::SetBitmap](../Topic/CMFCCaptionBar::SetBitmap.md)|Задает изображение растрового изображения для заголовка окна.|  
|[CMFCCaptionBar::SetBorderSize](../Topic/CMFCCaptionBar::SetBorderSize.md)|Задает размер границы заголовка окна.|  
|[CMFCCaptionBar::SetButton](../Topic/CMFCCaptionBar::SetButton.md)|Задает кнопку для заголовка окна.|  
|[CMFCCaptionBar::SetButtonPressed](../Topic/CMFCCaptionBar::SetButtonPressed.md)|Определяет, находится ли кнопка отображаемая нажатой.|  
|[CMFCCaptionBar::SetButtonToolTip](../Topic/CMFCCaptionBar::SetButtonToolTip.md)|Задает подсказку для кнопки.|  
|[CMFCCaptionBar::SetFlatBorder](../Topic/CMFCCaptionBar::SetFlatBorder.md)|Задает стиль границ заголовка окна.|  
|[CMFCCaptionBar::SetIcon](../Topic/CMFCCaptionBar::SetIcon.md)|Задает Значок для заголовка окна.|  
|[CMFCCaptionBar::SetImageToolTip](../Topic/CMFCCaptionBar::SetImageToolTip.md)|Задает подсказку для образа для заголовка окна.|  
|[CMFCCaptionBar::SetMargin](../Topic/CMFCCaptionBar::SetMargin.md)|Устанавливает расстояние между краем элемента управления и краем заголовка окна заголовка окна.|  
|[CMFCCaptionBar::SetText](../Topic/CMFCCaptionBar::SetText.md)|Задает текстовой подписи для заголовка окна.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCCaptionBar::OnDrawBackground](../Topic/CMFCCaptionBar::OnDrawBackground.md)|Вызывается средой выполнения для заполнения фона заголовка окна.|  
|[CMFCCaptionBar::OnDrawBorder](../Topic/CMFCCaptionBar::OnDrawBorder.md)|Вызывается средой выполнения для рисования границы заголовка окна.|  
|[CMFCCaptionBar::OnDrawButton](../Topic/CMFCCaptionBar::OnDrawButton.md)|Вызывается средой выполнения для создания кнопки заголовка окна.|  
|[CMFCCaptionBar::OnDrawImage](../Topic/CMFCCaptionBar::OnDrawImage.md)|Вызывается средой выполнения для создания образа заголовка окна.|  
|[CMFCCaptionBar::OnDrawText](../Topic/CMFCCaptionBar::OnDrawText.md)|Вызывается средой выполнения для отрисовки текста заголовка окна.|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCCaptionBar::m\_clrBarBackground](../Topic/CMFCCaptionBar::m_clrBarBackground.md)|Цвет фона заголовка окна.|  
|[CMFCCaptionBar::m\_clrBarBorder](../Topic/CMFCCaptionBar::m_clrBarBorder.md)|Цвет границы заголовка окна.|  
|[CMFCCaptionBar::m\_clrBarText](../Topic/CMFCCaptionBar::m_clrBarText.md)|Цвет текста заголовка окна.|  
  
## Заметки  
 Чтобы создать заголовок окна, выполните следующие действия.  
  
1.  Создайте объект `CMFCCaptionBar`.  Как правило, необходимо добавить заголовок окна в классе фреймового окна.  
  
2.  Вызовите метод [CMFCCaptionBar::Create](../Topic/CMFCCaptionBar::Create.md), чтобы создать элемент управления " заголовок окна " и вложить его в объект `CMFCCaptionBar`.  
  
3.  Вызовите [CMFCCaptionBar::SetButton](../Topic/CMFCCaptionBar::SetButton.md), [CMFCCaptionBar::SetText](../Topic/CMFCCaptionBar::SetText.md), [CMFCCaptionBar::SetIcon](../Topic/CMFCCaptionBar::SetIcon.md) и [CMFCCaptionBar::SetBitmap](../Topic/CMFCCaptionBar::SetBitmap.md) для размещения элементов заголовка окна.  
  
 При задании элементе кнопки, необходимо присвоить идентификатор команды к кнопке.  Когда пользователь нажимает кнопку, заголовок окна направляет сообщения `WM_COMMAND` с этим идентификатором фреймовому к родительскому окну.  
  
 Заголовок окна также может работать в режиме панели сообщений, эмулирующем запуск панель сообщений, которая отображается в Microsoft Office 2007 приложений.  В режиме панели сообщений, заголовок окна показаны растровое изображение, сообщение и кнопку \(которая обычно открывает диалоговое окно\). Можно присвоить подсказывает растрового изображения.  
  
 Чтобы включить режим панели сообщений, вызовите [CMFCCaptionBar::Create](../Topic/CMFCCaptionBar::Create.md) и задайте четвертый параметр \(bIsMessageBarMode\) значение `TRUE`.  
  
## Пример  
 В следующем примере показано, как использовать различные методы класса `CMFCCaptionBar`.  Пример показывает, как создать элемент управления заголовка окна, задайте трехмерную границу заголовка окна, задайте расстояние \(в пикселях\) между краем элемента управления и краем заголовка окна заголовка окна, набора кнопка для заголовка окна, задайте подсказки для кнопки, задайте текстовой подписи для заголовка окна, задайте образ растрового изображения для заголовка окна и укажите подсказку для образа в заголовке окна.  Этот фрагмент кода часть [Пример demo MS Office 2007](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#1](../../mfc/reference/codesnippet/CPP/cmfccaptionbar-class_1.h)]  
[!code-cpp[NVC_MFC_MSOffice2007Demo#2](../../mfc/reference/codesnippet/CPP/cmfccaptionbar-class_2.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)  
  
## Требования  
 **Заголовок:** afxcaptionbar.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)