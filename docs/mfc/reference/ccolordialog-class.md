---
title: "Класс CColorDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CColorDialog
- AFXDLGS/CColorDialog
- AFXDLGS/CColorDialog::CColorDialog
- AFXDLGS/CColorDialog::DoModal
- AFXDLGS/CColorDialog::GetColor
- AFXDLGS/CColorDialog::GetSavedCustomColors
- AFXDLGS/CColorDialog::SetCurrentColor
- AFXDLGS/CColorDialog::OnColorOK
- AFXDLGS/CColorDialog::m_cc
dev_langs:
- C++
helpviewer_keywords:
- colors, dialog box
- dialog boxes, colors
- CColorDialog class
ms.assetid: d013dc25-9290-4b5d-a97e-95ad7208e13b
caps.latest.revision: 25
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a8aee088aadbca18acda348c574c8f4b55d1ecbb
ms.lasthandoff: 02/24/2017

---
# <a name="ccolordialog-class"></a>Класс CColorDialog
Позволяет включить диалоговое окно выбора цвета в приложение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CColorDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CColorDialog::CColorDialog](#ccolordialog)|Создает объект `CColorDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CColorDialog::DoModal](#domodal)|Отображает диалоговое окно и позволяет пользователю сделать выбор.|  
|[CColorDialog::GetColor](#getcolor)|Возвращает **COLORREF** структура, содержащая значения выбранного цвета.|  
|[CColorDialog::GetSavedCustomColors](#getsavedcustomcolors)|Получает цвет, созданные пользователем.|  
|[CColorDialog::SetCurrentColor](#setcurrentcolor)|Вызывает текущий цвет для указанного цвета.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CColorDialog::OnColorOK](#oncolorok)|Переопределение для проверки введенных в диалоговом окне цвет.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CColorDialog::m_cc](#m_cc)|Структура, используемая для настройки параметров диалогового окна.|  
  
## <a name="remarks"></a>Примечания  
 Объект `CColorDialog` объект — это диалоговое окно со списком цветов, которые определены для системы отображения. Пользователя можно выбрать или создать конкретный цвет из списка и затем отправляются обратно в приложение при завершении диалоговое окно.  
  
 Для создания `CColorDialog` объекта, используйте предоставленный конструктор или наследовать новый класс и использовать собственный пользовательский конструктор.  
  
 После конструирования диалоговом окне можно задать или изменить какое-либо значение [m_cc](#m_cc) структуры для инициализации значений элементов управления диалогового окна. `m_cc` Структуры имеет тип [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830).  
  
 После инициализации диалогового окна элементы управления, вызовите метод `DoModal` функции-члена для отображения диалогового окна и позволяет пользователю выбрать цвет. `DoModal`Возвращает ОК диалогового окна выбора пользователя, либо ( **IDOK**) или Отмена ( **IDCANCEL**) кнопки.  
  
 Если `DoModal` возвращает **IDOK**, можно использовать один из `CColorDialog`функции-члены для извлечения информации, введенное пользователем.  
  
 Можно использовать окна [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) функции, чтобы определить, произошла ли ошибка во время инициализации диалогового окна и для получения дополнительных сведений об ошибке.  
  
 `CColorDialog`зависит от COMMDLG. DLL-файл, поставляемый с Windows версии 3.1 и более поздней версии.  
  
 Чтобы настроить диалоговое окно, создайте класс, производный от `CColorDialog`, предоставить шаблон пользовательское диалоговое окно и добавить схемы сообщений для обработки сообщений уведомления из расширенных элементов управления. Все необработанные сообщения должны передаваться в базовый класс.  
  
 Настройка функцию-обработчик не является обязательным.  
  
> [!NOTE]
>  В некоторых установках `CColorDialog` объекта не будет отображаться на сером фоне, при использовании платформы вносить другие `CDialog` объекты серый.  
  
 Дополнительные сведения об использовании `CColorDialog`, в разделе [классы общих диалоговых окон](../../mfc/common-dialog-classes.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CColorDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdlgs.h  
  
##  <a name="ccolordialog"></a>CColorDialog::CColorDialog  
 Создает объект `CColorDialog`.  
  
```  
CColorDialog(
    COLORREF clrInit = 0,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *clrInit*  
 Выбор цвета по умолчанию. Если значение не указано, значение по умолчанию — RGB(0,0,0) (черный).  
  
 `dwFlags`  
 Набор флагов, настроить внешний вид диалогового окна и функции. Дополнительные сведения см. в разделе [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pParentWnd`  
 Указатель на окне родительский или владельца диалогового окна.  
  
### <a name="example"></a>Пример  
 [!code-cpp[№&49; NVC_MFCDocView](../../mfc/codesnippet/cpp/ccolordialog-class_1.cpp)]  
  
##  <a name="domodal"></a>CColorDialog::DoModal  
 Эта функция вызывается для отображения диалогового окна Windows общих цветов и позволяет пользователю выбрать цвет.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **IDOK** или **IDCANCEL**. Если **IDCANCEL** будет возвращен, вызовите Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) функцию, чтобы определить, произошла ли ошибка.  
  
 **IDOK** и **IDCANCEL** константы, которые указывают, выбрал ли пользователь кнопку OK или "Отмена".  
  
### <a name="remarks"></a>Примечания  
 Если требуется инициализировать различные параметры диалогового окна цвет, задав члены [m_cc](#m_cc) структуры, это следует сделать до вызова метода `DoModal` , но после создания объекта диалоговых.  
  
 После вызова метода `DoModal`, можно вызвать другой член функции для получения параметров или данные, введенные пользователем в диалоговом окне.  
  
### <a name="example"></a>Пример  
  В примере показано [CColorDialog::CColorDialog](#ccolordialog).  
  
##  <a name="getcolor"></a>CColorDialog::GetColor  
 Эта функция вызывается после вызова метода `DoModal` для получения информации о выбранный пользователем цвет.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, содержащее сведения RGB для цвета, выбранного в диалоговом окне цветов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#50;](../../mfc/codesnippet/cpp/ccolordialog-class_2.cpp)]  
  
##  <a name="getsavedcustomcolors"></a>CColorDialog::GetSavedCustomColors  
 `CColorDialog`объекты позволяют пользователю, помимо выбора цвета, для определения пользовательских цветов до 16.  
  
```  
static COLORREF* PASCAL GetSavedCustomColors();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на массив 16 RGB-значения цветов, хранящая пользовательские цвета, созданные пользователем.  
  
### <a name="remarks"></a>Примечания  
 `GetSavedCustomColors` Функция-член обеспечивает доступ к эти цвета. Эти цвета можно получить после [DoModal](#domodal) возвращает **IDOK**.  
  
 Каждое значение 16 RGB в возвращаемый массив инициализируется RGB(255,255,255) (белый). Пользовательские цвета, выбранного пользователем, сохраняются только между вызовами диалоговое окно в приложении. Если вы хотите сохранить эти цвета между вызовами приложения, вам необходимо сохранить их иным способом, например в инициализации (. Файл INI).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#51;](../../mfc/codesnippet/cpp/ccolordialog-class_3.cpp)]  
  
##  <a name="m_cc"></a>CColorDialog::m_cc  
 Структура типа [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830), члены которого хранения характеристики и значения диалогового окна.  
  
```  
CHOOSECOLOR m_cc;  
```  
  
### <a name="remarks"></a>Примечания  
 После построения `CColorDialog` объекта, можно использовать `m_cc` для задания различных аспектов диалоговым окном перед вызовом метода [DoModal](#domodal) функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#53;](../../mfc/codesnippet/cpp/ccolordialog-class_4.cpp)]  
  
##  <a name="oncolorok"></a>CColorDialog::OnColorOK  
 Переопределение для проверки введенных в диалоговом окне цвет.  
  
```  
virtual BOOL OnColorOK();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если диалоговое окно не должно быть отброшено; в противном случае — 0, чтобы принять цвет, который был введен.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно переопределите только в том случае, если вы хотите предоставить пользовательскую проверку цвета, выбранного пользователем в диалоговом окне цвет.  
  
 Пользователь может выбрать цвет одним из следующих двух способов:  
  
-   Если щелкнуть цвет в палитре цветов. Выбранный цвет RGB-значения затем отображаются в соответствующих полях редактирования RGB.  
  
-   Ввод значений в формате RGB поля ввода  
  
 Переопределение `OnColorOK` позволяет отклонить цвета, пользователь вводит в общее диалоговое окно цвет для какой-либо причине конкретного приложения.  
  
 Обычно не нужно использовать эту функцию, так как платформа обеспечивает проверку по умолчанию цветов и отображает окно сообщения, если указан недопустимый цвет.  
  
 Можно вызвать [SetCurrentColor](#setcurrentcolor) изнутри `OnColorOK` для принудительного выбора цвета. Один раз `OnColorOK` произошло (то есть, пользователь нажимает кнопку **ОК** принять изменение цвета), можно вызвать [GetColor](#getcolor) для получения значения нового цвета RGB.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#52;](../../mfc/codesnippet/cpp/ccolordialog-class_5.cpp)]  
  
##  <a name="setcurrentcolor"></a>CColorDialog::SetCurrentColor  
 Эта функция вызывается после вызова метода `DoModal` для принудительного выбранный цвет, цвет значение, указанное в `clr`.  
  
```  
void SetCurrentColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Параметры  
 `clr`  
 Значение цвета RGB.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается из обработчика сообщений или `OnColorOK`. Диалоговое окно выбора пользователя, на основе значения автоматически обновляет `clr` параметр.  
  
### <a name="example"></a>Пример  
  В примере показано [CColorDialog::OnColorOK](#oncolorok).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MDI](../../visual-cpp-samples.md)   
 [Пример MFC ФУНКЦИЙ](../../visual-cpp-samples.md)   
 [Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)


