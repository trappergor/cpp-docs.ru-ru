---
title: "CMFCColorPickerCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCColorPickerCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorPickerCtrl class"
ms.assetid: b9bbd03c-beb0-4b55-9765-9985fd05e5dc
caps.latest.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 35
---
# CMFCColorPickerCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCColorPickerCtrl` предоставляет функциональные возможности для элемента управления, используемый для выбора цвета.  
  
## Синтаксис  
  
```  
class CMFCColorPickerCtrl : public CButton  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCColorPickerCtrl::CMFCColorPickerCtrl](../Topic/CMFCColorPickerCtrl::CMFCColorPickerCtrl.md)|Создает объект `CMFCColorPickerCtrl`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCColorPickerCtrl::GetColor](../Topic/CMFCColorPickerCtrl::GetColor.md)|Получает цвет, пользователь выбирает.|  
|[CMFCColorPickerCtrl::GetHLS](../Topic/CMFCColorPickerCtrl::GetHLS.md)|Извлекает значение оттенка, насыщенности и яркости цвета, пользователь выбирает.|  
|[CMFCColorPickerCtrl::GetHue](../Topic/CMFCColorPickerCtrl::GetHue.md)|Получает компонент оттенка цвета, пользователь выбирает.|  
|[CMFCColorPickerCtrl::GetLuminance](../Topic/CMFCColorPickerCtrl::GetLuminance.md)|Получает компонент яркости цвета, пользователь выбирает.|  
|[CMFCColorPickerCtrl::GetSaturation](../Topic/CMFCColorPickerCtrl::GetSaturation.md)|Получает компонент насыщенности цвета, пользователь выбирает.|  
|[CMFCColorPickerCtrl::SelectCellHexagon](../Topic/CMFCColorPickerCtrl::SelectCellHexagon.md)|Задает текущий цвет в качестве значения цвет, определенному указанным компонентов цвета RGB или указанным шестиугольником ячейки.|  
|[CMFCColorPickerCtrl::SetColor](../Topic/CMFCColorPickerCtrl::SetColor.md)|Задает текущий цвет равным заданному значению цвета RGB.|  
|[CMFCColorPickerCtrl::SetHLS](../Topic/CMFCColorPickerCtrl::SetHLS.md)|Задает текущий цвет равным заданному значению цвета HLS.|  
|[CMFCColorPickerCtrl::SetHue](../Topic/CMFCColorPickerCtrl::SetHue.md)|Изменяет компонент оттенка выбранного цвета.|  
|[CMFCColorPickerCtrl::SetLuminance](../Topic/CMFCColorPickerCtrl::SetLuminance.md)|Изменяет компонент яркости цвета, выбранного в данный момент.|  
|[CMFCColorPickerCtrl::SetLuminanceBarWidth](../Topic/CMFCColorPickerCtrl::SetLuminanceBarWidth.md)|Задает ширину панель яркости в элементе управления палитры.|  
|[CMFCColorPickerCtrl::SetOriginalColor](../Topic/CMFCColorPickerCtrl::SetOriginalColor.md)|Устанавливает цвет, выбранный инициалом.|  
|[CMFCColorPickerCtrl::SetPalette](../Topic/CMFCColorPickerCtrl::SetPalette.md)|Задает текущую цветовую палитру.|  
|[CMFCColorPickerCtrl::SetSaturation](../Topic/CMFCColorPickerCtrl::SetSaturation.md)|Изменяет компонент насыщенности выбранного цвета.|  
|[CMFCColorPickerCtrl::SetType](../Topic/CMFCColorPickerCtrl::SetType.md)|Задает тип элемента управления палитры для отображения.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCColorPickerCtrl::DrawCursor](../Topic/CMFCColorPickerCtrl::DrawCursor.md)|Вызывается инфраструктурой перед курсором, указывающий на выбранный цвет.|  
  
## Заметки  
 Стандартные цвета выделены из шестиугольной цветовой палитры, а дополнительные цвета выделены из области яркости цвета или где определены с использованием цветовых значений красного, зеленого и голубую нотации или нотацию оттенка\/satuaration и яркости.  
  
 На следующем рисунке показаны несколько объектов `CMFCColorPickerCtrl`.  
  
 ![Диалоговое окно для CMFCColorPickerCtrl](../../mfc/reference/media/colorpicker.png "ColorPicker")  
  
 Обозреватель `CMFCColorPickerCtrl` 2 пар стилей.  Стили и соответствующие ШЕСТНАДЦАТЕРИЧНЫЕ HEX\_GREYSCALE для стандартного выбора цвета.  Стили ВЫБОРА и ЯРКОСТИ подходят для выделения пользовательского цвета.  
  
 Выполните следующие шаги, чтобы включить `CMFCColorPickerCtrl` элемент управления в диалоговое окно.  
  
1.  При использовании **ClassWizard**, вставьте новый элемент управления "Кнопка" в шаблон диалогового окна \(поскольку класс `CMFCColorPickerCtrl` наследуется от класса `CButton` \).  
  
2.  Вставьте переменную участника, сопоставлена с новым элемент управления "Кнопка" в класс диалогового окна.  Затем измените тип переменной из `CButton` к `CMFCColorPickerCtrl`.  
  
3.  Вставьте обработчик сообщений `WM_INITDIALOG` для класса диалогового окна.  В обработчике задайте тип, палитру и initial выбранный цвет элемента управления `CMFCColorPickerCtrl`.  
  
## Пример  
 В следующем примере показано, как настроить объект `CMFCColorPickerCtrl` с помощью различных методов в классе `CMFCColorPickerCtrl`.  Примере показано, как задать тип элемента управления " выбор и установить его цвет, оттенок, насыщенность, а яркость.  Пример является частью [Создать образец элементов управления](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_NewControls#4](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#4)]  
[!CODE [NVC_MFC_NewControls#5](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#5)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)  
  
## Требования  
 **заголовок:** afxcolorpickerctrl.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCColorDialog Class](../../mfc/reference/cmfccolordialog-class.md)