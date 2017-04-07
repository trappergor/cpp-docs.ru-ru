---
title: "Класс CMFCEditBrowseCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCEditBrowseCtrl
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableFileBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableFolderBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::GetMode
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnAfterUpdate
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnBrowse
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnChangeLayout
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnDrawBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnIllegalFileName
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::SetBrowseButtonImage
dev_langs:
- C++
helpviewer_keywords:
- CMFCEditBrowseCtrl::PreTranslateMessage method
- CMFCEditBrowseCtrl constructor
- CMFCEditBrowseCtrl class
ms.assetid: 69cfd886-3d35-4bee-8901-7c88fcf9520f
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5c5650da677a442628049c9ef4b41c2142cfb2c2
ms.lasthandoff: 02/24/2017

---
# <a name="cmfceditbrowsectrl-class"></a>Класс CMFCEditBrowseCtrl
`CMFCEditBrowseCtrl` Класс поддерживает управления обзор редактирования, который является редактируемых текстовых полей, которые дополнительно содержат кнопку обзора. Когда пользователь нажимает кнопку обзора, элемент управления выполняет настраиваемое действие или отображает стандартное диалоговое окно, содержащее браузер файла или папки в браузере.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCEditBrowseCtrl : public CEdit  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCEditBrowseCtrl::CMFCEditBrowseCtrl`|Конструктор по умолчанию.|  
|`CMFCEditBrowseCtrl::~CMFCEditBrowseCtrl`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton)|Включает или отключает (скрывает) кнопку.|  
|[CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton)|Кнопка «Обзор» и помещает элемент управления для редактирования обзора в *Обзор файлов* режим.|  
|[CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton)|Кнопка «Обзор» и помещает элемент управления для редактирования обзора в *обзора папок* режим.|  
|[CMFCEditBrowseCtrl::GetMode](#getmode)|Возвращает текущий режим просмотра.|  
|[CMFCEditBrowseCtrl::OnAfterUpdate](#onafterupdate)|Вызывается платформой после обновления Обзор управления редактированием с результатом действие просмотра.|  
|[CMFCEditBrowseCtrl::OnBrowse](#onbrowse)|Вызывается платформой после нажатия кнопки «Обзор».|  
|[CMFCEditBrowseCtrl::OnChangeLayout](#onchangelayout)|Перерисовывает текущего элемента управления обзора редактирования.|  
|[CMFCEditBrowseCtrl::OnDrawBrowseButton](#ondrawbrowsebutton)|Вызывается платформой для рисования «Обзор».|  
|[CMFCEditBrowseCtrl::OnIllegalFileName](#onillegalfilename)|Вызывается платформой, если было введено неверное имя файла в элементе управления.|  
|`CMFCEditBrowseCtrl::PreTranslateMessage`|Преобразует оконных сообщений перед их отправкой [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) функции Windows. Синтаксис и Дополнительные сведения см. в разделе [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).|  
|[CMFCEditBrowseCtrl::SetBrowseButtonImage](#setbrowsebuttonimage)|Задает пользовательский образ для кнопки «Обзор».|  
  
## <a name="remarks"></a>Примечания  
 Использование элемента управления обзора выберите имя файла или папки. При необходимости используйте элемент управления для выполнения настраиваемого действия, например, чтобы отобразить диалоговое окно. Можно отображать или не отображать кнопку, и можно применить пользовательскую метку или изображения на кнопке.  
  
 *Режим просмотра* обзора редактирования элемента управления определяет ли оно отображает кнопку «Обзор» и выполняемое действие при нажатии кнопки. Дополнительные сведения см. в разделе [GetMode](#getmode) метод.  
  
 `CMFCEditBrowseCtrl` Класс поддерживает следующие режимы.  
  
 `custom mode`  
 Настраиваемое действие выполняется, когда пользователь нажимает кнопку обзора. Например можно отобразить диалоговое окно для конкретного приложения.  
  
 `file mode`  
 Когда пользователь щелкает кнопку, отображается диалоговое окно выбора стандартный файл.  
  
 `folder mode`  
 Диалоговое окно выбора стандартные папки отображается, когда пользователь нажимает кнопку обзора.  
  
## <a name="how-to-specify-an-edit-browse-control"></a>Практическое руководство: Укажите элемента управления обзора  
 Выполните следующие действия, чтобы включить элемент управления редактированием обзора в приложении.  
  
1.  Если требуется реализовать пользовательские обзора режим, создать собственный производный класс от `CMFCEditBrowseCtrl` класса, а затем переопределить [CMFCEditBrowseCtrl::OnBrowse](#onbrowse) метод. В переопределенном методе выполнить пользовательское действие просмотра и обновления Обзор управления редактированием с результатами.  
  
2.  Внедрение либо `CMFCEditBrowseCtrl` или объект элемента управления обзора производном редактирования в окне родительский объект.  
  
3.  Если вы используете **мастер классов** для создания диалогового окна, добавление элемента управления ( `CEdit`) в форме диалогового окна. Кроме того Добавьте переменную для доступа к элементу управления в файле заголовка. В файле заголовка, измените тип переменной из `CEdit` в `CMFCEditBrowseCtrl`. Обзор управления редактированием будут создаваться автоматически. Если вы не используете **мастер классов**, добавьте `CMFCEditBrowseCtrl` переменной в файл заголовка и затем вызвать его `Create` метод.  
  
4.  При добавлении элемента управления обзора диалоговому окну, используйте **ClassWizard** средства для настройки обмена данными.  
  
5.  Вызов [EnableFolderBrowseButton](#enablefolderbrowsebutton), [EnableFileBrowseButton](#enablefilebrowsebutton), или [EnableBrowseButton](#enablebrowsebutton) метод, чтобы задать режим просмотра и отобразить кнопку. Вызов [GetMode](#getmode) метод, чтобы получить текущий режим просмотра.  
  
6.  Для обеспечения пользовательского образа кнопку, вызовите [SetBrowseButtonImage](#setbrowsebuttonimage) метода или переопределение [OnDrawBrowseButton](#ondrawbrowsebutton) метод.  
  
7.  Чтобы удалить кнопку Обзор управления редактированием, вызовите [EnableBrowseButton](#enablebrowsebutton) метод `bEnable` параметра `FALSE`.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCEditBrowseCtrl](../../mfc/reference/cmfceditbrowsectrl-class.md)  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется использование двух методах `CMFCEditBrowseCtrl` класса: `EnableFolderBrowseButton` и `EnableFileBrowseButton`. Этот пример является частью [пример создания новых элементов управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls №&6;](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#7;](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_2.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxeditbrowsectrl.h  
  
##  <a name="enablebrowsebutton"></a>CMFCEditBrowseCtrl::EnableBrowseButton  
 Отображает или не отображает кнопку на текущий элемент управления редактирование обзора.  
  
```  
void EnableBrowseButton(
    BOOL bEnable=TRUE,  
    LPCTSTR szLabel=_T("..."));
```  
  
### <a name="parameters"></a>Параметры  
 `bEnable`  
 `TRUE`для отображения кнопки "Обзор". `FALSE` не требуется отображать кнопку. Значение по умолчанию — `TRUE`.  
  
 `szLabel`  
 Надпись, отображаемая на кнопку. Значение по умолчанию — « **... **".  
  
### <a name="remarks"></a>Примечания  
 Если `bEnable` параметр `TRUE`, реализовать пользовательское действие для выполнения при нажатии кнопки обзора. Чтобы реализовать пользовательское действие, создайте класс, производный от `CMFCEditBrowseCtrl` класса, а затем переопределить ее [OnBrowse](#onbrowse) метод.  
  
 Если `bEnable` параметр `TRUE`, находится в режиме просмотра элемента управления `BrowseMode_Default`; в противном случае — в режиме обзора `BrowseMode_None`. Дополнительные сведения о режимах просмотра см. в разделе [GetMode](#getmode) метод.  
  
##  <a name="enablefilebrowsebutton"></a>CMFCEditBrowseCtrl::EnableFileBrowseButton  
 Отображает кнопку на текущий элемент управления редактирование обзора и помещает элемент управления в *Обзор файлов* режим.  
  
```  
void EnableFileBrowseButton(
    LPCTSTR lpszDefExt=NULL,  
    LPCTSTR lpszFilter=NULL,  
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszDefExt`  
 Указывает расширение имени файла по умолчанию, используемое в диалоговом окне выбора файла. Значение по умолчанию — `NULL`.  
  
 `lpszFilter`  
 Указывает строку фильтра по умолчанию, используемую в диалоговом окне выбора файла. Значение по умолчанию — `NULL`.  
  
 `dwFlags`  
 Флаги диалогового окна. Значение по умолчанию представляет собой битовую комбинацию (OR) флагов OFN_HIDEREADONLY и OFN_OVERWRITEPROMPT.  
  
### <a name="remarks"></a>Примечания  
 Когда элемент управления "Обзор" находится в режиме поиска файлов, а пользователь нажимает кнопку обзора, элемент управления отображает стандартное диалоговое окно выбора файла.  
  
 Полный список доступных флагов см. в разделе [OPENFILENAME структуры](https://msdn.microsoft.com/library/ms646839.aspx).  
  
##  <a name="enablefolderbrowsebutton"></a>CMFCEditBrowseCtrl::EnableFolderBrowseButton  
 Отображает кнопку на текущий элемент управления редактирование обзора и помещает элемент управления в *обзора папок* режим.  
  
```  
void EnableFolderBrowseButton();
```  
  
### <a name="remarks"></a>Примечания  
 Если поле обзора редактирования находится в режиме просмотра папок и пользователь нажимает кнопку обзора, элемент управления отображает диалоговое окно выбора стандартные папки.  
  
##  <a name="getmode"></a>CMFCEditBrowseCtrl::GetMode  
 Получает режим просмотра текущего элемента управления обзора.  
  
```  
CMFCEditBrowseCtrl::BrowseMode GetMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из значений перечисления, указывающее текущий режим правки Обзор элемента управления. Режим просмотра определяет ли платформа отображает кнопку и выполняемое действие, когда пользователь нажимает эту кнопку.  
  
 В следующей таблице перечислены возможные возвращаемые значения.  
  
|Значение|Описание|  
|-----------|-----------------|  
|`BrowseMode_Default`|`custom mode`. Выполняется действие, определяемые программистом.|  
|`BrowseMode_File`|`file mode`. Откроется диалоговое окно браузера стандартный файл.|  
|`BrowseMode_Folder`|`folder mode`. Откроется диалоговое окно браузера стандартные папки.|  
|`BrowseMode_None`|«Обзор» не отображается.|  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `CMFCEditBrowseCtrl` объект инициализируется с `BrowseMode_None` режим. Изменить режим просмотра с [CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton), [CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton), и [CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton) методы.  
  
##  <a name="onafterupdate"></a>CMFCEditBrowseCtrl::OnAfterUpdate  
 Вызывается платформой после обновления Обзор управления редактированием с результатом действие просмотра.  
  
```  
virtual void OnAfterUpdate();
```  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское действие.  
  
##  <a name="onbrowse"></a>CMFCEditBrowseCtrl::OnBrowse  
 Вызывается платформой после нажатия кнопки "Обзор" Обзор элемента управления.  
  
```  
virtual void OnBrowse();
```  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для выполнения пользовательского кода, когда пользователь щелкает кнопку Обзор элемента управления. Создать собственный производный класс от `CMFCEditBrowseCtrl` класс и переопределите его `OnBrowse` метод. В этом методе реализовать пользовательское действие просмотра и при необходимости измените текстовое поле элемента управления обзора. В приложении, используйте [EnableBrowseButton](#enablebrowsebutton) метод для размещения элемента управления обзора редактирования *пользовательские Обзор* режим.  
  
##  <a name="onchangelayout"></a>CMFCEditBrowseCtrl::OnChangeLayout  
 Перерисовывает текущего элемента управления обзора редактирования.  
  
```  
virtual void OnChangeLayout();
```  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод при режиме просмотра для обзора редактирования управления изменениями. Дополнительные сведения см. в разделе [CMFCEditBrowseCtrl::GetMode](#getmode).  
  
##  <a name="ondrawbrowsebutton"></a>CMFCEditBrowseCtrl::OnDrawBrowseButton  
 Вызывается платформой для рисования кнопку Обзор управления редактированием.  
  
```  
virtual void OnDrawBrowseButton(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsButtonPressed,  
    BOOL bIsButtonHot);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства.  
  
 `Rect`  
 Ограничивающий прямоугольник кнопки «Обзор».  
  
 `bIsButtonPressed`  
 `TRUE`Если нажата кнопка; в противном случае — `FALSE`.  
  
 `bIsButtonHot`  
 `TRUE`Если кнопка выделена; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция в производном классе, чтобы настроить внешний вид кнопки Обзор переопределяется.  
  
##  <a name="setbrowsebuttonimage"></a>CMFCEditBrowseCtrl::SetBrowseButtonImage  
 Задает пользовательский образ на кнопку Обзор элемента управления.  
  
```  
void SetBrowseButtonImage(
    HICON hIcon,  
    BOOL bAutoDestroy= TRUE);

 
void SetBrowseButtonImage(
    HBITMAP hBitmap,  
    BOOL bAutoDestroy= TRUE);  
  
void SetBrowseButtonImage(UINT uiBmpResId);
```  
  
### <a name="parameters"></a>Параметры  
 `hIcon`  
 Дескриптор значка.  
  
 `hBitmap`  
 Дескриптор точечного рисунка.  
  
 `uiBmpResId`  
 Идентификатор ресурса растрового изображения.  
  
 `bAutoDestroy`  
 `TRUE`Чтобы удалить указанный значок или растровое изображение, при выходе этого метода; в противном случае — `FALSE`. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для применения образа к «Обзор». По умолчанию платформа получает стандартного образа, при щелчке элемента управления обзора редактирования в *Обзор файлов* или *обзора папок* режим.  
  
##  <a name="onillegalfilename"></a>CMFCEditBrowseCtrl::OnIllegalFileName  
 Вызывается платформой, если было введено неверное имя файла в элементе управления.  
  
```  
virtual BOOL OnIllegalFileName(CString& strFileName);
```  
  
### <a name="parameters"></a>Параметры  
 `strFileName`  
 Указывает неверное имя файла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Должен возвращать `FALSE` Если это имя файла не могут быть переданы дальше в диалоговом окне файла. В этом случае фокус перемещается обратно в элемент управления поля ввода, и пользователь должен продолжить редактирование. Реализация по умолчанию отображает окно сообщения, извещающее о неверное имя файла и возвращает `FALSE`. Переопределите этот метод, исправьте имя файла и возвращать `TRUE` для дальнейшей обработки.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)

