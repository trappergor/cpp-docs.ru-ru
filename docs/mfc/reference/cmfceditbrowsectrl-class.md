---
title: "Класс классе Mfceditbrowsectrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CMFCEditBrowseCtrl [MFC], EnableBrowseButton
- CMFCEditBrowseCtrl [MFC], EnableFileBrowseButton
- CMFCEditBrowseCtrl [MFC], EnableFolderBrowseButton
- CMFCEditBrowseCtrl [MFC], GetMode
- CMFCEditBrowseCtrl [MFC], OnAfterUpdate
- CMFCEditBrowseCtrl [MFC], OnBrowse
- CMFCEditBrowseCtrl [MFC], OnChangeLayout
- CMFCEditBrowseCtrl [MFC], OnDrawBrowseButton
- CMFCEditBrowseCtrl [MFC], OnIllegalFileName
- CMFCEditBrowseCtrl [MFC], SetBrowseButtonImage
ms.assetid: 69cfd886-3d35-4bee-8901-7c88fcf9520f
caps.latest.revision: "33"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ceca13bd09483c788c430d420b53c88bb97ed34d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cmfceditbrowsectrl-class"></a>Класс классе Mfceditbrowsectrl
`CMFCEditBrowseCtrl` Класс поддерживает Обзор элемента управления редактирования, используемый редактируемых текстовых полей, которые дополнительно содержат кнопку обзора. Когда пользователь нажимает кнопку обзора, элемент управления выполняет настраиваемое действие или отображает стандартное диалоговое окно, содержащее браузер файла или папки в браузере.  
  
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
|[CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton)|Включает или отключает (скрывает) кнопку обзора.|  
|[CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton)|Кнопка «Обзор» и помещает в поле редактирования обзора *Обзор файлов* режим.|  
|[CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton)|Кнопка «Обзор» и помещает в поле редактирования обзора *обзора папок* режим.|  
|[CMFCEditBrowseCtrl::GetMode](#getmode)|Возвращает текущий режим обзора.|  
|[CMFCEditBrowseCtrl::OnAfterUpdate](#onafterupdate)|Вызывается структурой после редактирования элемента управления обзора обновляется с результатом действия обзора.|  
|[CMFCEditBrowseCtrl::OnBrowse](#onbrowse)|Вызывается платформой при нажатии кнопки «Обзор».|  
|[CMFCEditBrowseCtrl::OnChangeLayout](#onchangelayout)|Перерисовывает текущего элемента управления Правка обзора.|  
|[CMFCEditBrowseCtrl::OnDrawBrowseButton](#ondrawbrowsebutton)|Вызывается платформой для прорисовки кнопки обзора.|  
|[CMFCEditBrowseCtrl::OnIllegalFileName](#onillegalfilename)|Вызывается платформой, если было введено недопустимое имя файла в поле редактирования.|  
|`CMFCEditBrowseCtrl::PreTranslateMessage`|Преобразует сообщения окна перед их передачей [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) функции Windows. Синтаксис и Дополнительные сведения см. в разделе [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).|  
|[CMFCEditBrowseCtrl::SetBrowseButtonImage](#setbrowsebuttonimage)|Задает пользовательского изображения для кнопки «Обзор».|  
  
## <a name="remarks"></a>Примечания  
 Используйте элемент управления редактированием обзора, чтобы выбрать имя файла или папки. При необходимости используйте элемент управления для выполнения пользовательского действия, например, чтобы отобразить диалоговое окно. Можно отображать или не отображать кнопку обзора, и можно применить пользовательскую метку или изображения на кнопке.  
  
 *Режим просмотра* обзора редактирования элемента управления определяет, отображается ли кнопка обзора и действие, которое происходит при нажатии кнопки. Дополнительные сведения см. в разделе [GetMode](#getmode) метод.  
  
 `CMFCEditBrowseCtrl` Класс поддерживает следующие режимы.  
  
 `custom mode`  
 Настраиваемое действие выполняется в том случае, когда пользователь нажимает кнопку обзора. Например можно отобразить диалоговое окно для конкретного приложения.  
  
 `file mode`  
 Диалоговое окно выбора стандартный файл отображается в том случае, когда пользователь нажимает кнопку обзора.  
  
 `folder mode`  
 Диалоговое окно выбора стандартные папки отображается в том случае, когда пользователь нажимает кнопку обзора.  
  
## <a name="how-to-specify-an-edit-browse-control"></a>Практическое руководство: Укажите элемент управления редактированием обзора  
 Выполните следующие действия, чтобы включить элемент управления редактированием обзора в приложении.  
  
1.  Если требуется реализовать пользовательские обзора режим создания собственного производного класса от `CMFCEditBrowseCtrl` класса и затем переопределить [CMFCEditBrowseCtrl::OnBrowse](#onbrowse) метод. В переопределенном методе выполнить пользовательское действие просмотра и обновления Обзор управления редактирования результатом.  
  
2.  Внедрение либо `CMFCEditBrowseCtrl` объект или объект элемента управления обзора производном изменения в родительском объекте окна.  
  
3.  Если вы используете **мастер классов** для создания диалогового окна, добавьте элемент управления редактированием ( `CEdit`) в форме диалогового окна. Кроме того Добавьте переменную для доступа к элементу управления в файле заголовка. В файле заголовка, измените тип переменной из `CEdit` для `CMFCEditBrowseCtrl`. Обзор управления редактирования будет создана автоматически. Если вы не используете **мастер классов**, добавьте `CMFCEditBrowseCtrl` переменной в файл заголовка и затем вызовите его `Create` метод.  
  
4.  При добавлении элемента управления обзора диалоговым окном, используйте **ClassWizard** средства для настройки обмена данными.  
  
5.  Вызовите [EnableFolderBrowseButton](#enablefolderbrowsebutton), [EnableFileBrowseButton](#enablefilebrowsebutton), или [EnableBrowseButton](#enablebrowsebutton) метод, чтобы задать режим просмотра и отображения кнопки "Обзор". Вызовите [GetMode](#getmode) метод, чтобы получить текущий режим обзора.  
  
6.  Для предоставления пользовательского изображения для кнопки обзора, вызовите [SetBrowseButtonImage](#setbrowsebuttonimage) метода или переопределение [OnDrawBrowseButton](#ondrawbrowsebutton) метод.  
  
7.  Чтобы удалить кнопку из элемента управления Правка обзора, вызовите [EnableBrowseButton](#enablebrowsebutton) метод с `bEnable` равным `FALSE`.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [Классе Mfceditbrowsectrl](../../mfc/reference/cmfceditbrowsectrl-class.md)  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует использование двух методов `CMFCEditBrowseCtrl` класса: `EnableFolderBrowseButton` и `EnableFileBrowseButton`. Данный пример является частью [образец новые элементы управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#6](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#7](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_2.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxeditbrowsectrl.h  
  
##  <a name="enablebrowsebutton"></a>CMFCEditBrowseCtrl::EnableBrowseButton  
 Отображает или не отображает кнопку обзора для текущего элемента управления Правка обзора.  
  
```  
void EnableBrowseButton(
    BOOL bEnable=TRUE,  
    LPCTSTR szLabel=_T("..."));
```  
  
### <a name="parameters"></a>Параметры  
 `bEnable`  
 `TRUE`для отображения кнопки "Обзор". `FALSE` не требуется отображать кнопку обзора. Значение по умолчанию — `TRUE`.  
  
 `szLabel`  
 Надпись, отображаемая на кнопку обзора. Значение по умолчанию — " **...** ".  
  
### <a name="remarks"></a>Примечания  
 Если `bEnable` параметр `TRUE`, реализация настраиваемого действия для выполнения, когда нажата кнопка "Обзор". Чтобы реализовать пользовательское действие, создайте класс, производный от `CMFCEditBrowseCtrl` класса, а затем переопределить ее [OnBrowse](#onbrowse) метод.  
  
 Если `bEnable` параметр `TRUE`, находится в режиме просмотра элемента управления `BrowseMode_Default`; в противном случае — режим просмотра `BrowseMode_None`. Дополнительные сведения о режимах просмотра см. в разделе [GetMode](#getmode) метод.  
  
##  <a name="enablefilebrowsebutton"></a>CMFCEditBrowseCtrl::EnableFileBrowseButton  
 Отображает кнопку обзора для текущего элемента управления Правка обзора и переводит элемент управления в *Обзор файлов* режим.  
  
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
  
 Полный список доступных флагов см. в разделе [структура OPENFILENAME](https://msdn.microsoft.com/library/ms646839.aspx).  
  
##  <a name="enablefolderbrowsebutton"></a>CMFCEditBrowseCtrl::EnableFolderBrowseButton  
 Отображает кнопку обзора для текущего элемента управления Правка обзора и переводит элемент управления в *обзора папок* режим.  
  
```  
void EnableFolderBrowseButton();
```  
  
### <a name="remarks"></a>Примечания  
 Если поле редактирования обзора находится в режиме просмотра папок и пользователь нажимает кнопку обзора, элемент управления отображает диалоговое окно выбора стандартные папки.  
  
##  <a name="getmode"></a>CMFCEditBrowseCtrl::GetMode  
 Возвращает режим обзора текущего элемента управления обзора.  
  
```  
CMFCEditBrowseCtrl::BrowseMode GetMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из значений перечисления, указывающее текущий режим правки Обзор элемента управления. Режим просмотра определяет, является ли платформа отображает кнопку обзора и действие, которое возникает, когда пользователь нажимает эту кнопку.  
  
 В следующей таблице перечислены возможные возвращаемые значения.  
  
|Значение|Описание|  
|-----------|-----------------|  
|`BrowseMode_Default`|`custom mode`. Выполняется действие, определяемые программистом.|  
|`BrowseMode_File`|`file mode`. Откроется диалоговое окно браузера стандартный файл.|  
|`BrowseMode_Folder`|`folder mode`. Откроется диалоговое окно браузера стандартные папки.|  
|`BrowseMode_None`|«Обзор» не отображается.|  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `CMFCEditBrowseCtrl` для инициализации объекта `BrowseMode_None` режим. Изменение режима обзора с [CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton), [CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton), и [CMFCEditBrowseCtrl::EnableFolderBrowseButton ](#enablefolderbrowsebutton) методы.  
  
##  <a name="onafterupdate"></a>CMFCEditBrowseCtrl::OnAfterUpdate  
 Вызывается структурой после редактирования элемента управления обзора обновляется с результатом действия обзора.  
  
```  
virtual void OnAfterUpdate();
```  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, чтобы реализовать пользовательское действие.  
  
##  <a name="onbrowse"></a>CMFCEditBrowseCtrl::OnBrowse  
 Вызывается платформой при нажатии кнопки "Обзор" Обзор элемента управления.  
  
```  
virtual void OnBrowse();
```  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для выполнения пользовательского кода, когда пользователь нажимает кнопку обзора Обзор элемента управления. Создать собственный класс, от `CMFCEditBrowseCtrl` класса и переопределить его `OnBrowse` метод. В этом методе реализовать пользовательское действие просмотра и при необходимости измените текстовое поле элемента управления обзора. В приложении, используйте [EnableBrowseButton](#enablebrowsebutton) метод, чтобы поместить в поле редактирования обзора *пользовательские обзора* режим.  
  
##  <a name="onchangelayout"></a>CMFCEditBrowseCtrl::OnChangeLayout  
 Перерисовывает текущего элемента управления Правка обзора.  
  
```  
virtual void OnChangeLayout();
```  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод при режиме просмотра для обзора редактирования контроля изменений. Дополнительные сведения см. в разделе [CMFCEditBrowseCtrl::GetMode](#getmode).  
  
##  <a name="ondrawbrowsebutton"></a>CMFCEditBrowseCtrl::OnDrawBrowseButton  
 Вызывается платформой для отрисовки «Обзор» в поле редактирования обзора.  
  
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
 Ограничивающий прямоугольник "Обзор".  
  
 `bIsButtonPressed`  
 `TRUE`При нажатии кнопки; в противном случае `FALSE`.  
  
 `bIsButtonHot`  
 `TRUE`Если кнопка выделена; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию в производном классе, чтобы настроить внешний вид «Обзор».  
  
##  <a name="setbrowsebuttonimage"></a>CMFCEditBrowseCtrl::SetBrowseButtonImage  
 Задает пользовательского изображения на кнопке обзора Обзор элемента управления.  
  
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
 Дескриптор растрового изображения.  
  
 `uiBmpResId`  
 Идентификатор ресурса точечного рисунка.  
  
 `bAutoDestroy`  
 `TRUE`для удаления указанного значка или точечного рисунка, если этот метод завершает работу; в противном случае `FALSE`. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для применения образа к кнопке обзора. По умолчанию платформа получает стандартный образ, при возможности редактирования элемента управления обзора *Обзор файлов* или *обзора папок* режим.  
  
##  <a name="onillegalfilename"></a>CMFCEditBrowseCtrl::OnIllegalFileName  
 Вызывается платформой, если было введено недопустимое имя файла в поле редактирования.  
  
```  
virtual BOOL OnIllegalFileName(CString& strFileName);
```  
  
### <a name="parameters"></a>Параметры  
 `strFileName`  
 Задает недопустимое имя файла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Должен возвращать `FALSE` Если это имя файла не может передаваться Далее для диалогового окна файла. В этом случае снова установить фокус на элемент управления для редактирования, и пользователь должен продолжить редактирование. Реализация по умолчанию отображает окно сообщения, извещающее о неверное имя файла и возвращает `FALSE`. Переопределите этот метод, исправьте имя файла и вернуть `TRUE` для дальнейшей обработки.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)
