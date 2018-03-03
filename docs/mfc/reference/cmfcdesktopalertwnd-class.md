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
- CMFCDesktopAlertWnd [MFC], Create
- CMFCDesktopAlertWnd [MFC], GetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], GetAnimationType
- CMFCDesktopAlertWnd [MFC], GetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], GetCaptionHeight
- CMFCDesktopAlertWnd [MFC], GetDialogSize
- CMFCDesktopAlertWnd [MFC], GetLastPos
- CMFCDesktopAlertWnd [MFC], GetTransparency
- CMFCDesktopAlertWnd [MFC], HasSmallCaption
- CMFCDesktopAlertWnd [MFC], OnBeforeShow
- CMFCDesktopAlertWnd [MFC], OnClickLinkButton
- CMFCDesktopAlertWnd [MFC], OnCommand
- CMFCDesktopAlertWnd [MFC], OnDraw
- CMFCDesktopAlertWnd [MFC], ProcessCommand
- CMFCDesktopAlertWnd [MFC], SetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], SetAnimationType
- CMFCDesktopAlertWnd [MFC], SetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], SetSmallCaption
- CMFCDesktopAlertWnd [MFC], SetTransparency
ms.assetid: 73a2dd7b-ea84-4ae2-9830-7cf6e8dd2425
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cfebb488921d81c36f842885ad49eae3f40a37fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcdesktopalertwnd-class"></a>CMFCDesktopAlertWnd Class
`CMFCDesktopAlertWnd` Класс реализует функции немодального диалогового окно, которое отображается на экране, чтобы информировать пользователей о событии.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]    
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCDesktopAlertWnd : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCDesktopAlertWnd::Create](#create)|Создает и инициализирует окно оповещения.|  
|[CMFCDesktopAlertWnd::GetAnimationSpeed](#getanimationspeed)|Возвращает скорость анимации.|  
|[CMFCDesktopAlertWnd::GetAnimationType](#getanimationtype)|Возвращает тип анимации.|  
|[CMFCDesktopAlertWnd::GetAutoCloseTime](#getautoclosetime)|Возвращает время ожидания автоматическое закрытие.|  
|[CMFCDesktopAlertWnd::GetCaptionHeight](#getcaptionheight)|Возвращает высоту заголовка.|  
|[CMFCDesktopAlertWnd::GetDialogSize](#getdialogsize)||  
|[CMFCDesktopAlertWnd::GetLastPos](#getlastpos)|Возвращает позицию последнего допустимым окно оповещения на экране.|  
|[CMFCDesktopAlertWnd::GetTransparency](#gettransparency)|Возвращает уровень прозрачности.|  
|[CMFCDesktopAlertWnd::HasSmallCaption](#hassmallcaption)|Определяет, отображается ли окно оповещения с маленького заголовка.|  
|[CMFCDesktopAlertWnd::OnBeforeShow](#onbeforeshow)||  
|[CMFCDesktopAlertWnd::OnClickLinkButton](#onclicklinkbutton)|Вызывается платформой, когда пользователь щелкает ссылку, расположенную меню рабочего стола предупреждения.|  
|[CMFCDesktopAlertWnd::OnCommand](#oncommand)|Платформа вызывает эту функцию-член, когда пользователь выбирает элемент меню, если дочерний элемент управления будет отправлять уведомления о или сочетаний клавиш нажатие клавиши преобразуется. (Переопределяет [CWnd::OnCommand](../../mfc/reference/cwnd-class.md#oncommand).)|  
|[CMFCDesktopAlertWnd::OnDraw](#ondraw)||  
|[CMFCDesktopAlertWnd::ProcessCommand](#processcommand)||  
|[CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed)|Задает новый скорость анимации.|  
|[CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype)|Задает тип анимации.|  
|[CMFCDesktopAlertWnd::SetAutoCloseTime](#setautoclosetime)|Задает время ожидания автоматическое закрытие.|  
|[CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption)|Переключение между малого и обычных заголовков.|  
|[CMFCDesktopAlertWnd::SetTransparency](#settransparency)|Задает уровень прозрачности.|  
  
## <a name="remarks"></a>Примечания  
 Окно оповещения может быть прозрачным, он может отображаться с эффектами анимации и он может исчезнуть (с заданной задержкой или когда пользователь закрывает его, нажав кнопку «Закрыть»).  
  
 Окно оповещения также может содержать диалогового окна по умолчанию, в свою очередь содержит значок, текст сообщения (метки) и ссылки. Кроме того окно оповещения может содержать настраиваемое диалоговое окно из ресурсов приложения.  
  
 Создать окно оповещения в два этапа. Во-первых, вызовите конструктор для создания `CMFCDesktopAlertWnd` объекта. Во-вторых, вызовите [CMFCDesktopAlertWnd::Create](#create) функции-члена для создания окна и присоединить его к `CMFCDesktopAlertWnd` объекта.  
  
 `CMFCDesktopAlertWnd` Объект создает специальные дочерние диалоговым окном, которое заполняет клиентскую область окно оповещения. Диалоговое окно является владельцем всех элементов управления, расположенные на нем.  
  
 Чтобы отобразить пользовательское диалоговое окно во всплывающем окне, выполните следующие действия:  
  
1.  Создайте производный класс от класса `CMFCDesktopAlertDialog`.  
  
2.  Создайте шаблон дочернего диалогового окна в ресурсах.  
  
3.  Вызовите [CMFCDesktopAlertWnd::Create](#create) с помощью идентификатора ресурс шаблона диалоговых окон и указатель на сведения о классе среды выполнения производного класса.  
  
4.  Создайте пользовательское диалоговое окно для обработки всех уведомлений, поступающих от размещенных элементов управления, или размещенные элементы управления для обработки этих уведомлений напрямую.  
  
 Следующие функции используются для управления поведением окно оповещения:  
  
-   Задать тип анимации, вызвав [CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype). Допустимые значения: unfold слайда и эффект затухания.  
  
-   Задать скорость кадров анимации, вызвав [CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed).  
  
-   Установить уровень прозрачности путем вызова [CMFCDesktopAlertWnd::SetTransparency](#settransparency).  
  
-   Измените размер заголовка на небольших путем вызова [CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption). Меньшего заголовка — 7 пикселей в высоту.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует использование различных методов `CMFCDesktopAlertWnd` класса, чтобы настроить `CMFCDesktopAlertWnd` объекта. Пример показано, как задать тип анимации, прозрачность всплывающего окна, укажите, что окно оповещения отображает меньшего заголовка и время, по истечении которого автоматически закрывает окно оповещения. В примере также показано создание и инициализация окно оповещения. Этот фрагмент кода является частью [Desktop предупреждения демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#1](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwnd-class_1.cpp)]  
  
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
 Указывает владельца окно оповещения. Этот владелец будет получать все уведомления о окно оповещения. Это значение не может быть равно `NULL`.  
  
 [in] `uiDlgResID`  
 Указывает идентификатор ресурса окно оповещения.  
  
 [in] `hMenu`  
 Задает меню, которое будет отображаться при нажатии кнопки меню. Если `NULL`, кнопка меню не отображается.  
  
 [in] `ptPos`  
 Указывает начальное положение, где отображается окно оповещения, с помощью координат экрана. Если этот параметр имеет (-1, -1), в правом нижнем углу экрана отображается окно оповещения.  
  
 [in] `pRTIDlgBar`  
 Сведения о классе среды выполнения, охватывающую клиентской области окна оповещений класса настраиваемое диалоговое окно.  
  
 [in] `params`  
 Указывает параметры, используемые для создания окне оповещения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если окно оповещения был создан успешно. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для создания окне оповещения. Клиентской области окна оповещения содержит дочернего диалогового окна, все элементы управления, отображаемых для пользователя.  
  
 Первая перегрузка метода создает окне оповещения, содержащий дочерние диалоговым окном, которое загружается из ресурсов приложения. Первая перегрузка метода можно также указать сведения о классе среды выполнения для класса пользовательского диалогового окна.  
  
 Вторая перегрузка метода создает окно оповещения, который содержит элементы управления по умолчанию. Можно указать, какие элементы управления должны отображаться, изменив [класс CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md).  
  
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
 Одно из следующих типов анимации:  
  
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
 Время в миллисекундах, после чего автоматически закроется окно оповещения.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы определить, сколько времени, по истечении которого автоматически закроется окно оповещения.  
  
##  <a name="getcaptionheight"></a>CMFCDesktopAlertWnd::GetCaptionHeight  
 Возвращает высоту заголовка.  
  
```  
virtual int GetCaptionHeight();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота в пикселях заголовка.  
  
### <a name="remarks"></a>Примечания  
 Этот метод может быть переопределен в производном классе. Реализация по умолчанию либо: возвращает значение высоту меньшего заголовка (7 в пикселях), если всплывающего окна должно отображаться меньшего заголовка, или значение, полученное от функции Windows API `GetSystemMetrics(SM_CYSMCAPTION)`.  
  
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
 Используйте этот метод для извлечения текущего уровня прозрачности окно оповещения.  
  
##  <a name="hassmallcaption"></a>CMFCDesktopAlertWnd::HasSmallCaption  
 Определяет, имеет ли окно оповещения меньшего заголовка или заголовка обычного размера.  
  
```  
BOOL HasSmallCaption() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если во всплывающем окне отображается с меньшего заголовка; `FALSE` Если во всплывающем окне отображается с заголовком обычный.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для определения наличия меньшего заголовка или обычного размера заголовок всплывающего окна. По умолчанию меньшего заголовка — 7 пикселей в высоту. Высоту заголовка обычного размера можно получить путем вызова функции Windows API `GetSystemMetrics(SM_CYCAPTION)`.  
  
##  <a name="onbeforeshow"></a>CMFCDesktopAlertWnd::OnBeforeShow  

  
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

  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="processcommand"></a>CMFCDesktopAlertWnd::ProcessCommand  

  
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
 Указывает новый скорость анимации в миллисекундах.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы задать скорость анимации в окне предупреждения. Скорость анимации по умолчанию — 30 миллисекунд.  
  
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
 Окно оповещения автоматически закрывается после указанного времени, если пользователь не будет взаимодействовать с окном.  
  
##  <a name="setsmallcaption"></a>CMFCDesktopAlertWnd::SetSmallCaption  
 Переключение между малого и обычного размера заголовков.  
  
```  
void SetSmallCaption(BOOL bSmallCaption = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bSmallCaption`  
 `TRUE`для указания, что окно оповещения отображает меньшего заголовка; в противном случае `FALSE` для указания, что окно оповещения отображается заголовок обычного размера.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для отображения небольших или обычный размер заголовка. По умолчанию меньшего заголовка — 7 пикселей в высоту. Размер заголовка регулярного можно получить путем вызова функции Windows API `GetSystemMetrics(SM_CYCAPTION)`.  
  
##  <a name="settransparency"></a>CMFCDesktopAlertWnd::SetTransparency  
 Задает уровень прозрачности во всплывающем окне.  
  
```  
void SetTransparency(BYTE nTransparency);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nTransparency`  
 Задает уровень прозрачности. Это значение должно быть в диапазоне от 0 до 255 включительно. Чем больше значение, более непрозрачный окна.  
  
### <a name="remarks"></a>Примечания  
 Вызывайте эту функцию, чтобы установить уровень прозрачности во всплывающем окне.  
  
##  <a name="getdialogsize"></a>CMFCDesktopAlertWnd::GetDialogSize  

  
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
 [Класс CWnd](../../mfc/reference/cwnd-class.md)
