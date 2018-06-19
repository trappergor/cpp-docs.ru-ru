---
title: Класс CMFCColorDialog | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMFCColorDialog [MFC], CMFCColorDialog
- CMFCColorDialog [MFC], GetColor
- CMFCColorDialog [MFC], GetPalette
- CMFCColorDialog [MFC], RebuildPalette
- CMFCColorDialog [MFC], SetCurrentColor
- CMFCColorDialog [MFC], SetNewColor
- CMFCColorDialog [MFC], SetPageOne
- CMFCColorDialog [MFC], SetPageTwo
ms.assetid: 235bbbbc-a3b1-46e0-801b-fb55093ec579
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 21114a3c04f96f2867f5440d47e856958060233e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367920"
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
|`CMFCColorDialog::PreTranslateMessage`|Преобразует сообщения окна перед их передачей [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) функции Windows. Синтаксис и Дополнительные сведения см. в разделе [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Переопределяет `CDialogEx::PreTranslateMessage`.)|  
|[CMFCColorDialog::RebuildPalette](#rebuildpalette)|Является производным палитру из системной палитры.|  
|[CMFCColorDialog::SetCurrentColor](#setcurrentcolor)|Задает текущий выбранный цвет.|  
|[CMFCColorDialog::SetNewColor](#setnewcolor)|Задает цвет, наиболее эквивалентных указанное значение RGB.|  
|[CMFCColorDialog::SetPageOne](#setpageone)|Выбирает значение RGB для первой страницы свойств.|  
|[CMFCColorDialog::SetPageTwo](#setpagetwo)|Выбирает значение RGB для второй страницы свойств.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|`m_bIsMyPalette`|`TRUE` Если в диалоговом окне выбора цвета использует свою собственную цветовую палитру или `FALSE` использует ли диалоговое окно палитры, которая указана в `CMFCColorDialog` конструктора.|  
|`m_bPickerMode`|`TRUE` Хотя пользователь выбирает цвет в диалоговом окне выбора; в противном случае `FALSE`.|  
|`m_btnColorSelect`|Кнопка цвета, выбранный пользователем.|  
|`m_CurrentColor`|Выбранный цвет.|  
|`m_hcurPicker`|Курсор, который используется для выбора цвета.|  
|`m_NewColor`|Потенциального выбранного цвета, который без возможности восстановления выбранные или восстановить исходное значение цвета.|  
|`m_pColourSheetOne`|Указатель на первую страницу свойств страницы свойств выбора цвета.|  
|`m_pColourSheetTwo`|Указатель на вторую страницу свойств, свойств, выбора цвета.|  
|`m_pPalette`|Текущий логическую палитру.|  
|`m_pPropSheet`|Указатель на страницу свойств в диалоговом окне выбора цвета.|  
|`m_wndColors`|Объект управления выбора цвета.|  
|`m_wndStaticPlaceHolder`|Статический элемент управления, — это заполнитель для страницы свойств средства выбора цвета.|  
  
## <a name="remarks"></a>Примечания  
 Окно выбора цвета отображается как окно свойств с двумя страницами. На первой странице выберите стандартный цвет из палитры системы; на второй странице можно выбрать другой цвет.  
  
 Можно создать `CMFCColorDialog` объекта в стеке, а затем вызвать `DoModal`, передав начальный цвет в качестве параметра для `CMFCColorDialog` конструктор. Окно выбора цвета создаются [класса для CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md) объектов для обработки каждого цвета палитры.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как настроить с помощью различных методов в диалоговом окне выбора цвета `CMFCColorDialog` класса. В примере показано, как задать текущую и отображения новых цветов диалогового окна и способ настройки компонентов красного, зеленого и синего цвета, выбранного на страницах свойств два цвета диалогового окна. Данный пример является частью [образец новые элементы управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#3](../../mfc/reference/codesnippet/cpp/cmfccolordialog-class_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcolordialog.h  
  
##  <a name="cmfccolordialog"></a>  CMFCColorDialog::CMFCColorDialog  
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
 (Зарезервирован.)  
  
 [in] `pParentWnd`  
 Указатель на диалоговое окно родительского или владельца.  
  
 [in] `hPal`  
 Дескриптор палитры цветов.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcolor"></a>  CMFCColorDialog::GetColor  
 Получает цвет, пользователем из диалогового окна цвет.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, которое содержит сведения для цвета, выбранного в диалоговом окне цветов RGB.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается после вызова метода `DoModal` метод.  
  
##  <a name="getpalette"></a>  CMFCColorDialog::GetPalette  
 Возвращает цветовую палитру, доступные в текущем диалоговом окне цвет.  
  
```  
CPalette* GetPalette() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CPalette` объект, который был указан в `CMFCColorDialog` конструктора.  
  
### <a name="remarks"></a>Примечания  
 Указывает, цветовую палитру цветов, которые пользователь может выбрать.  
  
##  <a name="rebuildpalette"></a>  CMFCColorDialog::RebuildPalette  
 Является производным палитру из системной палитры.  
  
```  
void RebuildPalette();
```  
  
##  <a name="setcurrentcolor"></a>  CMFCColorDialog::SetCurrentColor  
 Задает цвет текущего диалогового окна.  
  
```  
void SetCurrentColor(COLORREF rgb);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rgb`  
 Значение RGB  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setnewcolor"></a>  CMFCColorDialog::SetNewColor  
 Задает текущий цвет в текущей палитре, наиболее подходящий цвет.  
  
```  
void SetNewColor(COLORREF rgb);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rgb`  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) , указывающий цвета RGB.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setpageone"></a>  CMFCColorDialog::SetPageOne  
 Явно указывает компонентов красного, зеленого и синего цвета, выбранные на первой странице Свойства диалогового окна "цвета".  
  
```  
void SetPageOne(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `R`  
 Указывает RGB-значение красного компонента.  
  
 [in] `G`  
 Задает зеленый компонент значения RGB.  
  
 [in] `B`  
 Указывает RGB-значение синего компонента.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setpagetwo"></a>  CMFCColorDialog::SetPageTwo  
 Явно указывает компонентов красного, зеленого и синего цвета, выбранного на странице свойств второй цвет диалогового окна.  
  
```  
void SetPageTwo(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `R`  
 Указывает красного компонента RGB-значение  
  
 [in] `G`  
 Указывает зеленого компонента RGB-значение  
  
 [in] `B`  
 Указывает синего компонента значение RGB  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)
