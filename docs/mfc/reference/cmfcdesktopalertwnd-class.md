---
title: "Класс CMFCDesktopAlertWnd | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::Create
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetCaptionHeight
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetDialogSize
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetLastPos
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetTransparency
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::HasSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnBeforeShow
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnClickLinkButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnDraw
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::ProcessCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetTransparency
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertWnd class
ms.assetid: 73a2dd7b-ea84-4ae2-9830-7cf6e8dd2425
caps.latest.revision: 33
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
ms.openlocfilehash: be9d81ffff003119aa7ff9e0cd100c575bd82d36
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdesktopalertwnd-class"></a>CMFCDesktopAlertWnd Class
`CMFCDesktopAlertWnd` Класс реализует функции немодального диалогового окно, которое отображается на экране, пользователь получает уведомление о событии.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCDesktopAlertWnd : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCDesktopAlertWnd::Create](#create)|Создает и инициализирует окно оповещения.|  
|[CMFCDesktopAlertWnd::GetAnimationSpeed](#getanimationspeed)|Возвращает скорость анимации.|  
|[CMFCDesktopAlertWnd::GetAnimationType](#getanimationtype)|Возвращает тип анимации.|  
|[CMFCDesktopAlertWnd::GetAutoCloseTime](#getautoclosetime)|Возвращает время ожидания автоматическое закрытие.|  
|[CMFCDesktopAlertWnd::GetCaptionHeight](#getcaptionheight)|Возвращает высоту заголовка.|  
|[CMFCDesktopAlertWnd::GetDialogSize](#getdialogsize)||  
|[CMFCDesktopAlertWnd::GetLastPos](#getlastpos)|Возвращает последний допустимый позицию окно оповещения на экране.|  
|[CMFCDesktopAlertWnd::GetTransparency](#gettransparency)|Возвращает уровень прозрачности.|  
|[CMFCDesktopAlertWnd::HasSmallCaption](#hassmallcaption)|Определяет, отображается ли окно оповещения с меньшего заголовка.|  
|[CMFCDesktopAlertWnd::OnBeforeShow](#onbeforeshow)||  
|[CMFCDesktopAlertWnd::OnClickLinkButton](#onclicklinkbutton)|Вызывается платформой, когда пользователь щелкает ссылку, расположенную меню рабочего стола предупреждения.|  
|[CMFCDesktopAlertWnd::OnCommand](#oncommand)|При выборе пользователем элемента меню, когда дочерний элемент управления будет отправлять уведомления о или при переводе сочетания клавиш, платформа вызывает эту функцию-член. (Переопределяет [CWnd::OnCommand](../../mfc/reference/cwnd-class.md#oncommand).)|  
|[CMFCDesktopAlertWnd::OnDraw](#ondraw)||  
|[CMFCDesktopAlertWnd::ProcessCommand](#processcommand)||  
|[CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed)|Задает новый скорость анимации.|  
|[CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype)|Задает тип анимации.|  
|[CMFCDesktopAlertWnd::SetAutoCloseTime](#setautoclosetime)|Задает время ожидания автоматическое закрытие.|  
|[CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption)|Переключение между небольшим и обычные заголовки.|  
|[CMFCDesktopAlertWnd::SetTransparency](#settransparency)|Задает уровень прозрачности.|  
  
## <a name="remarks"></a>Примечания  
 Окно оповещения может быть прозрачным, он может отображаться с эффектами анимации и исчезают (после заданной задержки или когда пользователь закрывает его, нажав кнопку «Закрыть»).  
  
 Окно оповещения также могут содержать диалоговое окно по умолчанию, который в свою очередь содержит значок, текст сообщения (метка) и ссылки. Кроме того окно оповещения может содержать пользовательское диалоговое окно из ресурсов приложения.  
  
 Создать окно оповещения в два этапа. Во-первых, вызовите конструктор для создания `CMFCDesktopAlertWnd` объекта. Во-вторых, вызовите [CMFCDesktopAlertWnd::Create](#create) функции-члена для создания окна и присоединить его к `CMFCDesktopAlertWnd` объекта.  
  
 `CMFCDesktopAlertWnd` Объект создает специальные дочерние диалоговым окном, которое заполняет область клиента окно оповещения. Диалоговое окно является владельцем всех элементов управления, расположенные на нем.  
  
 Чтобы отобразить пользовательское диалоговое окно во всплывающем окне, выполните следующие действия.  
  
1.  Создайте производный класс от класса `CMFCDesktopAlertDialog`.  
  
2.  Создайте шаблон дочернего диалогового окна в ресурсах.  
  
3.  Вызов [CMFCDesktopAlertWnd::Create](#create) с помощью идентификатора ресурса из шаблонов диалоговых окон и указатель на данные класса среды выполнения производного класса.  
  
4.  Программа пользовательские диалоговые окна для обработки всех уведомлений, поступающих от размещенные элементы управления или программа размещенные элементы управления непосредственно обрабатывать эти уведомления.  
  
 Следующие функции используются для управления поведением окно оповещения:  
  
-   Задать тип анимации, вызвав [CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype). Допустимые значения: unfold слайда и эффект затухания.  
  
-   Установить скорость кадров анимации путем вызова [CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed).  
  
-   Установить уровень прозрачности путем вызова [CMFCDesktopAlertWnd::SetTransparency](#settransparency).  
  
-   Изменить размер заголовка для небольших путем вызова [CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption). Меньшего заголовка — 7 пикселов в высоту.  
  
## <a name="example"></a>Пример  
 Следующий пример показывает, как использовать различные методы в `CMFCDesktopAlertWnd` класс для настройки `CMFCDesktopAlertWnd` объекта. Пример показано, как задать тип анимации, прозрачности всплывающего окна, укажите, что окно оповещения отображает малого заголовка и задать время, по истечении которого автоматически закрывает окно оповещения. В примере также показано создание и инициализация окно оповещения. Этот фрагмент кода является частью [рабочего стола предупреждения демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo&#1;](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwnd-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxDesktopAlertWnd.h  
  
##  <a name="create"></a>CMFCDesktopAlertWnd::Create  
 Создает и инициализирует окно оповещения.  
  
```  
virtual BOOL Create(
    CWnd* pWndOwner,  
    UINT uiDlgResID,  
    HMENU hMenu = NULL,  
    CPoint ptPos = CPoint(-1,-1),  
    CRuntimeClass* pRTIDlgBar = RUNTIME_CLASS(CMFCDesktopAlertDialog));

 
virtual BOOL Create(
    CWnd* pWndOwner,  
    CMFCDesktopAlertWndInfo& params,  
    HMENU hMenu = NULL,  
    CPoint ptPos = CPoint(-1,-1));
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out]`pWndOwner`  
 Указывает владельца окно оповещения. Этот владелец затем получает все уведомления для окно оповещения. Это значение не может быть равно `NULL`.  
  
 [in] `uiDlgResID`  
 Указывает идентификатор ресурса окно оповещения.  
  
 [in] `hMenu`  
 Указывает меню, которое отображается при нажатии пользователем кнопки меню. Если `NULL`, кнопка меню не отображается.  
  
 [in] `ptPos`  
 Определяет начальное положение, где отображается окно оповещения, с помощью координат экрана. Если этот параметр (-1, -1), в правом нижнем углу экрана отображается окно оповещения.  
  
 [in] `pRTIDlgBar`  
 Сведения о класса среды выполнения для класс пользовательского диалогового окна, охватывающую клиентской области окна оповещений.  
  
 [in] `params`  
 Указывает параметры, используемые для создания окне оповещения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если окно оповещения был создан успешно. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для создания окне оповещения. Клиентской области окна оповещений содержит дочерние диалоговым окном, которое размещает все элементы управления, которые отображаются для пользователя.  
  
 Первая перегрузка метода создает окне оповещения, содержащий дочерние диалоговым окном, которое загружается из ресурсов приложения. Первая перегрузка метода можно также указать сведения о классах среды выполнения для класса пользовательского диалогового окна.  
  
 Вторая перегрузка метода создает окно оповещения, который содержит элементы управления по умолчанию. Можно указать, какие элементы управления должны отображаться, изменив [CMFCDesktopAlertWndInfo класса](../../mfc/reference/cmfcdesktopalertwndinfo-class.md).  
  
##  <a name="getanimationspeed"></a>CMFCDesktopAlertWnd::GetAnimationSpeed  
 Возвращает скорость анимации.  
  
```  
UINT GetAnimationSpeed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Скорость анимации окно оповещения, в миллисекундах.  
  
### <a name="remarks"></a>Примечания  
 Скорость анимации описывает, как быстро окно оповещения открывает и закрывает.  
  
##  <a name="getanimationtype"></a>CMFCDesktopAlertWnd::GetAnimationType  
 Возвращает тип анимации.  
  
```  
CMFCPopupMenu::ANIMATION_TYPE GetAnimationType();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из следующих типов анимации:  
  
- `NO_ANIMATION`  
  
- `UNFOLD`  
  
- `SLIDE`  
  
- `FADE`  
  
- `SYSTEM_DEFAULT_ANIMATION`  
  
##  <a name="getautoclosetime"></a>CMFCDesktopAlertWnd::GetAutoCloseTime  
 Возвращает время ожидания автоматическое закрытие.  
  
```  
int GetAutoCloseTime() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Время в миллисекундах, после чего автоматически закроет окно оповещения.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы определить, сколько времени должно пройти, прежде чем автоматически закроет окно оповещения.  
  
##  <a name="getcaptionheight"></a>CMFCDesktopAlertWnd::GetCaptionHeight  
 Возвращает высоту заголовка.  
  
```  
virtual int GetCaptionHeight();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота в пикселях заголовка.  
  
### <a name="remarks"></a>Примечания  
 Этот метод может быть переопределен в производном классе. Реализация по умолчанию либо: возвращает значение высоту меньшего заголовка (7 точек), если всплывающего окна должно отображаться меньшего заголовка, или значение, полученное от функции Windows API `GetSystemMetrics(SM_CYSMCAPTION)`.  
  
##  <a name="getlastpos"></a>CMFCDesktopAlertWnd::GetLastPos  
 Возвращает позицию последнего окно оповещения на экране.  
  
```  
CPoint GetLastPos() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Точка, в экранных координатах.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает позицию последнего допустимый предупреждения окна на экране.  
  
##  <a name="gettransparency"></a>CMFCDesktopAlertWnd::GetTransparency  
 Возвращает уровень прозрачности.  
  
```  
BYTE GetTransparency() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Уровень прозрачности от 0 до 255 включительно. Чем больше значение, более непрозрачный окна.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы получить текущий уровень прозрачности окно оповещения.  
  
##  <a name="hassmallcaption"></a>CMFCDesktopAlertWnd::HasSmallCaption  
 Определяет, имеет ли окно оповещения малого заголовка или заголовок обычного размера.  
  
```  
BOOL HasSmallCaption() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если во всплывающем окне отображается с меньшего заголовка; `FALSE` если всплывающее окно отображается с надписью обычный.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для определения наличия меньшего заголовка или обычного размера заголовок всплывающего окна. По умолчанию меньшего заголовка — 7 пикселов в высоту. Высота заголовка обычного размера можно получить, вызвав функцию Windows API `GetSystemMetrics(SM_CYCAPTION)`.  
  
##  <a name="onbeforeshow"></a>CMFCDesktopAlertWnd::OnBeforeShow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnBeforeShow(CPoint&);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `CPoint&`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onclicklinkbutton"></a>CMFCDesktopAlertWnd::OnClickLinkButton  
 Вызывается платформой, когда пользователь щелкает ссылку, расположенную меню рабочего стола предупреждения.  
  
```  
virtual BOOL OnClickLinkButton(UINT uiCmdID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdID`  
 Этот параметр не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, если вы хотите получать уведомления, когда пользователь щелкает ссылку на окно оповещения.  
  
##  <a name="oncommand"></a>CMFCDesktopAlertWnd::OnCommand  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnCommand(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `wParam`  
 [in] `lParam`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondraw"></a>CMFCDesktopAlertWnd::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="processcommand"></a>CMFCDesktopAlertWnd::ProcessCommand  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL ProcessCommand(HWND hwnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hwnd`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setanimationspeed"></a>CMFCDesktopAlertWnd::SetAnimationSpeed  
 Задает новый скорость анимации.  
  
```  
void SetAnimationSpeed(UINT nSpeed);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nSpeed`  
 Указывает новый скорость анимации, в миллисекундах.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для установки скорости анимации для окна оповещения. Скорость анимации по умолчанию — 30 миллисекунд.  
  
##  <a name="setanimationtype"></a>CMFCDesktopAlertWnd::SetAnimationType  
 Задает тип анимации.  
  
```  
void SetAnimationType(CMFCPopupMenu::ANIMATION_TYPE type);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `type`  
 Указывает тип анимации.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для задания типа анимации. Можно указать одно из следующих значений.  
  
- `NO_ANIMATION`  
  
- `UNFOLD`  
  
- `SLIDE`  
  
- `FADE`  
  
- `SYSTEM_DEFAULT_ANIMATION`  
  
##  <a name="setautoclosetime"></a>CMFCDesktopAlertWnd::SetAutoCloseTime  
 Задает время ожидания автоматическое закрытие.  
  
```  
void SetAutoCloseTime(int nTime);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nTime`  
 Время в миллисекундах, прошедшее до автоматически закрывает окно оповещения.  
  
### <a name="remarks"></a>Примечания  
 Окно оповещения автоматически закрывается после указанного времени, если пользователь не взаимодействует с окном.  
  
##  <a name="setsmallcaption"></a>CMFCDesktopAlertWnd::SetSmallCaption  
 Переключение между небольшим и обычного размера заголовков.  
  
```  
void SetSmallCaption(BOOL bSmallCaption = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSmallCaption`  
 `TRUE`Чтобы указать, что окно оповещения отображает малого заголовка; в противном случае — `FALSE` для указания, что окно предупреждения отображается заголовок обычного размера.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для отображения заголовка небольшого или обычного размера. По умолчанию меньшего заголовка — 7 пикселов в высоту. Размер заголовка регулярных можно получить путем вызова функции Windows API `GetSystemMetrics(SM_CYCAPTION)`.  
  
##  <a name="settransparency"></a>CMFCDesktopAlertWnd::SetTransparency  
 Задает уровень прозрачности всплывающего окна.  
  
```  
void SetTransparency(BYTE nTransparency);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nTransparency`  
 Определяет уровень прозрачности. Это значение должно быть в диапазоне от 0 до 255 включительно. Чем больше значение, более непрозрачный окна.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для установки уровня прозрачности всплывающего окна.  
  
##  <a name="getdialogsize"></a>CMFCDesktopAlertWnd::GetDialogSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetDialogSize();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)   
 [Класс CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)

