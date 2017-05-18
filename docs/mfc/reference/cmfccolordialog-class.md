---
title: "Класс CMFCColorDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::GetColor
- AFXCOLORDIALOG/CMFCColorDialog::GetPalette
- AFXCOLORDIALOG/CMFCColorDialog::RebuildPalette
- AFXCOLORDIALOG/CMFCColorDialog::SetCurrentColor
- AFXCOLORDIALOG/CMFCColorDialog::SetNewColor
- AFXCOLORDIALOG/CMFCColorDialog::SetPageOne
- AFXCOLORDIALOG/CMFCColorDialog::SetPageTwo
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorDialog::m_CurrentColor data member
- CMFCColorDialog::m_pPropSheet data member
- CMFCColorDialog::m_btnColorSelect data member
- CMFCColorDialog class
- CMFCColorDialog::m_wndColors data member
- CMFCColorDialog::m_bIsMyPalette data member
- CMFCColorDialog::m_pColourSheetTwo data member
- CMFCColorDialog::m_NewColor data member
- CMFCColorDialog::m_pPalette data member
- CMFCColorDialog::m_wndStaticPlaceHolder data member
- CMFCColorDialog::m_pColourSheetOne data member
- CMFCColorDialog::m_hcurPicker data member
- CMFCColorDialog::PreTranslateMessage method
- CMFCColorDialog::m_bPickerMode data member
ms.assetid: 235bbbbc-a3b1-46e0-801b-fb55093ec579
caps.latest.revision: 30
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ac621157e0fcb5bcabef2ae8f367a1b141b4ace0
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolordialog-class"></a>Класс CMFCColorDialog
`CMFCColorDialog` Класс представляет диалоговое окно выбора цвета.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCColorDialog : public CDialogEx  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCColorDialog::CMFCColorDialog](#cmfccolordialog)|Создает объект `CMFCColorDialog`.|  
|`CMFCColorDialog::~CMFCColorDialog`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCColorDialog::GetColor](#getcolor)|Возвращает текущий выбранный цвет.|  
|[CMFCColorDialog::GetPalette](#getpalette)|Возвращает цветовую палитру.|  
|`CMFCColorDialog::PreTranslateMessage`|Преобразует оконных сообщений перед их отправкой [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) функции Windows. Синтаксис и Дополнительные сведения см. в разделе [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Переопределяет `CDialogEx::PreTranslateMessage`.)|  
|[CMFCColorDialog::RebuildPalette](#rebuildpalette)|Палитра наследует палитры системы.|  
|[CMFCColorDialog::SetCurrentColor](#setcurrentcolor)|Задает текущий выбранный цвет.|  
|[CMFCColorDialog::SetNewColor](#setnewcolor)|Задает цвет наиболее соответствует указанное значение RGB.|  
|[CMFCColorDialog::SetPageOne](#setpageone)|Выбирает значение RGB для первой страницы свойств.|  
|[CMFCColorDialog::SetPageTwo](#setpagetwo)|Выбирает значение RGB для второй страницы свойств.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|`m_bIsMyPalette`|`TRUE`Если диалоговое окно выбора цвета использует свою собственную цветовую палитру или `FALSE` использует ли диалоговое окно палитры, которая указана в `CMFCColorDialog` конструктора.|  
|`m_bPickerMode`|`TRUE`Хотя пользователь выбирает цвет в диалоговом окне выбора; в противном случае — `FALSE`.|  
|`m_btnColorSelect`|Кнопка цвет, выбранный пользователем.|  
|`m_CurrentColor`|Выбранный цвет.|  
|`m_hcurPicker`|Курсор, который используется для выбора цвета.|  
|`m_NewColor`|Потенциальный выбранного цвета, которой постоянно выбран или вернуть исходное значение цвета.|  
|`m_pColourSheetOne`|Указатель на первую страницу свойств страницы свойств для выбора цвета.|  
|`m_pColourSheetTwo`|Указатель на вторую страницу свойств страницы свойств для выбора цвета.|  
|`m_pPalette`|Текущий логический палитры.|  
|`m_pPropSheet`|Указатель на страницу свойств диалоговое окно выбора цвета.|  
|`m_wndColors`|Объект управления выбора цвета.|  
|`m_wndStaticPlaceHolder`|Статический элемент управления, — это окно свойств цвета палитры.|  
  
## <a name="remarks"></a>Примечания  
 Диалоговое окно выбора цвета отображаются в виде свойств, с двумя страницами. На первой странице выберите стандартный цвет из палитры системы; на второй странице можно выбрать другой цвет.  
  
 Можно создать `CMFCColorDialog` объекта в стеке, а затем вызвать `DoModal`, передав цвет в качестве параметра `CMFCColorDialog` конструктор. Диалоговое окно выбора цвета создаются [для CMFCColorPickerCtrl класс](../../mfc/reference/cmfccolorpickerctrl-class.md) объектов для обработки каждой цветовой палитры.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует настройки с помощью различных методов в диалоговом окне цветов `CMFCColorDialog` класса. В примере показано, как задать текущий и новых цветов в диалоговом окне и задание красного, зеленого и синего компонентов выбранного цвета на двух свойств в диалоговом окне цвет. Этот пример является частью [пример создания новых элементов управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#3;](../../mfc/reference/codesnippet/cpp/cmfccolordialog-class_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcolordialog.h  
  
##  <a name="cmfccolordialog"></a>CMFCColorDialog::CMFCColorDialog  
 Создает объект `CMFCColorDialog`.  
  
```  
CMFCColorDialog(
    COLORREF clrInit=0,  
    DWORD dwFlags=0,  
    CWnd* pParentWnd=NULL,  
    HPALETTE hPal=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `clrInit`  
 Выбор цвета по умолчанию. Если значение не указано, значение по умолчанию — RGB(0,0,0) (черный).  
  
 [in] `dwFlags`  
 (Зарезервировано).  
  
 [in] `pParentWnd`  
 Указатель на окне родительский или владельца диалогового окна.  
  
 [in] `hPal`  
 Дескриптор палитры.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcolor"></a>CMFCColorDialog::GetColor  
 Получает цвет, выбранный пользователем в диалоговом окне цвет.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, содержащее сведения RGB для цвета, выбранного в диалоговом окне цветов.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода `DoModal` метод.  
  
##  <a name="getpalette"></a>CMFCColorDialog::GetPalette  
 Возвращает цветовую палитру, которая доступна в диалоговом окне текущий цвет.  
  
```  
CPalette* GetPalette() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CPalette` объекта, который был указан в `CMFCColorDialog` конструктора.  
  
### <a name="remarks"></a>Примечания  
 Цветовая палитра указывает цветов, которые пользователь может выбрать.  
  
##  <a name="rebuildpalette"></a>CMFCColorDialog::RebuildPalette  
 Палитра наследует палитры системы.  
  
```  
void RebuildPalette();
```  
  
##  <a name="setcurrentcolor"></a>CMFCColorDialog::SetCurrentColor  
 Задает текущий цвет диалогового окна.  
  
```  
void SetCurrentColor(COLORREF rgb);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rgb`  
 RGB-значение цвета  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setnewcolor"></a>CMFCColorDialog::SetNewColor  
 Задает текущий цвет цвет в палитре текущего, наиболее подходящий.  
  
```  
void SetNewColor(COLORREF rgb);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rgb`  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) , указывающий цвета RGB.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setpageone"></a>CMFCColorDialog::SetPageOne  
 Явно указывает красного, зеленого и синего компонентов выбранного цвета на первой странице свойство цвета диалогового окна.  
  
```  
void SetPageOne(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `R`  
 Задает красный компонент значения RGB.  
  
 [in] `G`  
 Задает зеленый компонент значения RGB.  
  
 [in] `B`  
 Задает синий компонент значения RGB.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setpagetwo"></a>CMFCColorDialog::SetPageTwo  
 Явно указывает красного, зеленого и синего компонентов выбранного цвета на второй странице свойство цвета диалогового окна.  
  
```  
void SetPageTwo(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `R`  
 Задает красный компонент значения RGB  
  
 [in] `G`  
 Задает зеленый компонент RGB-значение  
  
 [in] `B`  
 Задает синий компонент RGB-значение  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс для CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)

