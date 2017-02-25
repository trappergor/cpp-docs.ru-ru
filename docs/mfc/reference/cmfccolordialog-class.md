---
title: "CMFCColorDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCColorDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorDialog class"
  - "CMFCColorDialog::m_bIsMyPalette data member"
  - "CMFCColorDialog::m_bPickerMode data member"
  - "CMFCColorDialog::m_btnColorSelect data member"
  - "CMFCColorDialog::m_CurrentColor data member"
  - "CMFCColorDialog::m_hcurPicker data member"
  - "CMFCColorDialog::m_NewColor data member"
  - "CMFCColorDialog::m_pColourSheetOne data member"
  - "CMFCColorDialog::m_pColourSheetTwo data member"
  - "CMFCColorDialog::m_pPalette data member"
  - "CMFCColorDialog::m_pPropSheet data member"
  - "CMFCColorDialog::m_wndColors data member"
  - "CMFCColorDialog::m_wndStaticPlaceHolder data member"
  - "CMFCColorDialog::PreTranslateMessage method"
ms.assetid: 235bbbbc-a3b1-46e0-801b-fb55093ec579
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCColorDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCColorDialog` представляет диалоговое окно выбора цвета.  
  
## Синтаксис  
  
```  
class CMFCColorDialog : public CDialogEx  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCColorDialog::CMFCColorDialog](../Topic/CMFCColorDialog::CMFCColorDialog.md)|Создает объект `CMFCColorDialog`.|  
|`CMFCColorDialog::~CMFCColorDialog`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCColorDialog::GetColor](../Topic/CMFCColorDialog::GetColor.md)|Возвращает цвет, выбранный в настоящий момент.|  
|[CMFCColorDialog::GetPalette](../Topic/CMFCColorDialog::GetPalette.md)|Возвращает палитру цветов.|  
|`CMFCColorDialog::PreTranslateMessage`|Преобразует сообщения окна до их посланы к функциям [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows.  Синтаксис и дополнительные сведения см. в разделе [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).  \(Переопределяет `CDialogEx::PreTranslateMessage`\).|  
|[CMFCColorDialog::RebuildPalette](../Topic/CMFCColorDialog::RebuildPalette.md)|Производный палитру из палитры системы.|  
|[CMFCColorDialog::SetCurrentColor](../Topic/CMFCColorDialog::SetCurrentColor.md)|Устанавливает цвет, выбранный в настоящий момент.|  
|[CMFCColorDialog::SetNewColor](../Topic/CMFCColorDialog::SetNewColor.md)|Устанавливает цвет большинство эквивалентно заданному rgb.|  
|[CMFCColorDialog::SetPageOne](../Topic/CMFCColorDialog::SetPageOne.md)|Выбирает значения rgb для первой страницы свойств.|  
|[CMFCColorDialog::SetPageTwo](../Topic/CMFCColorDialog::SetPageTwo.md)|Выбирает значения rgb для второй страницы свойств.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|`m_bIsMyPalette`|`TRUE` если диалоговое окно выбора цвета использует собственную цветовую палитру или `FALSE` если диалоговое окно используется палитру, которая определена в конструкторе `CMFCColorDialog`.|  
|`m_bPickerMode`|`TRUE` когда пользователь выбирает цвет из диалогового окна выбора; в противном случае – значение `FALSE`.|  
|`m_btnColorSelect`|Кнопка цвета, пользователь выбрал.|  
|`m_CurrentColor`|Выбранный цвет.|  
|`m_hcurPicker`|Курсор, используемый для выбора цвета.|  
|`m_NewColor`|Предполагаемый выбранный цвет, который можно окончательно выбрать или отменить изменения к исходному цвет.|  
|`m_pColourSheetOne`|Указатель на первой странице свойств страницы свойств выбора цвета.|  
|`m_pColourSheetTwo`|Указатель на второй странице свойств страницы свойств выбора цвета.|  
|`m_pPalette`|Текущая логической палитры.|  
|`m_pPropSheet`|Указатель на странице свойств для диалогового окна выбора цвета.|  
|`m_wndColors`|Объект управления палитры.|  
|`m_wndStaticPlaceHolder`|Статический элемент управления, заполнитель для страницы свойств палитры.|  
  
## Заметки  
 Диалоговое окно выбора цвета показано, как страница свойств с 2 страницами.  На первой странице, выберите стандартный цвет в палитре системы; на второй странице можно выбрать пользовательский цвет.  
  
 Можно создать объект `CMFCColorDialog` в стеке, а затем вызвать `DoModal`, указав начальный цвет в качестве параметра конструктору `CMFCColorDialog`.  Диалоговое окно выбора цвета затем создает несколько объектов [CMFCColorPickerCtrl Class](../../mfc/reference/cmfccolorpickerctrl-class.md) для обработки каждой цветовой палитры.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  
  
## Пример  
 В следующем примере показано, как настроить диалоговое окно цвет с использованием различных методов в классе `CMFCColorDialog`.  Примере показано, как задать текущую и новые цвета диалогового окна, и, как задать красного, зеленого и синего компонентов выбранного цвета на 2 страницах свойств диалогового окна цвета.  Данный пример является частью [Создать образец элементов управления](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#3](../../mfc/reference/codesnippet/CPP/cmfccolordialog-class_1.cpp)]  
  
## Требования  
 **заголовок:** afxcolordialog.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCColorPickerCtrl Class](../../mfc/reference/cmfccolorpickerctrl-class.md)