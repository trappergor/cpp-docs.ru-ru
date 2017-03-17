---
title: "Диалоговое окно CFindReplaceDialog класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::Create
- AFXDLGS/CFindReplaceDialog::FindNext
- AFXDLGS/CFindReplaceDialog::GetFindString
- AFXDLGS/CFindReplaceDialog::GetNotifier
- AFXDLGS/CFindReplaceDialog::GetReplaceString
- AFXDLGS/CFindReplaceDialog::IsTerminating
- AFXDLGS/CFindReplaceDialog::MatchCase
- AFXDLGS/CFindReplaceDialog::MatchWholeWord
- AFXDLGS/CFindReplaceDialog::ReplaceAll
- AFXDLGS/CFindReplaceDialog::ReplaceCurrent
- AFXDLGS/CFindReplaceDialog::SearchDown
- AFXDLGS/CFindReplaceDialog::m_fr
dev_langs:
- C++
helpviewer_keywords:
- text searches, replacing text
- text searches, CFindReplaceDialog class
- Find/Replace dialog box
- replacing text, CFindReplaceDialog class
- CFindReplaceDialog class
- replacing text
ms.assetid: 610f0b5d-b398-4ef6-8c05-e9d6641e50a8
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
ms.openlocfilehash: 510f6a763dbacb7d4e1b14ea808a4baaaf3d6bf3
ms.lasthandoff: 02/24/2017

---
# <a name="cfindreplacedialog-class"></a>Диалоговое окно CFindReplaceDialog класса
Позволяет реализовать стандартную строку поиска и замены диалоговых окон в приложении.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CFindReplaceDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog)|Эта функция вызывается для создания `CFindReplaceDialog` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFindReplaceDialog::Create](#create)|Создает и отображает `CFindReplaceDialog` диалоговое окно.|  
|[CFindReplaceDialog::FindNext](#findnext)|Эта функция вызывается для определения, хочет ли пользователь найти следующее вхождение строки поиска.|  
|[CFindReplaceDialog::GetFindString](#getfindstring)|Эта функция вызывается для получения текущей строки поиска.|  
|[CFindReplaceDialog::GetNotifier](#getnotifier)|Эта функция вызывается для получения **FINDREPLACE** структуры в обработчике зарегистрированных сообщений.|  
|[CFindReplaceDialog::GetReplaceString](#getreplacestring)|Эта функция вызывается для получения текущей строки замены.|  
|[CFindReplaceDialog::IsTerminating](#isterminating)|Эта функция вызывается для определения, завершает ли работу диалоговое окно.|  
|[CFindReplaceDialog::MatchCase](#matchcase)|Эта функция используется для определения, является ли пользователь хочет точно соответствовать регистру строки поиска.|  
|[CFindReplaceDialog::MatchWholeWord](#matchwholeword)|Эта функция вызывается для определения, хочет ли пользователь слова целиком.|  
|[CFindReplaceDialog::ReplaceAll](#replaceall)|Эта функция вызывается для определения ли пользователю все вхождения строки замены.|  
|[CFindReplaceDialog::ReplaceCurrent](#replacecurrent)|Эта функция вызывается для определения ли пользователю текущее слово для замены.|  
|[CFindReplaceDialog::SearchDown](#searchdown)|Эта функция вызывается для определения, хочет ли пользователь поиска, чтобы перейти вниз.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFindReplaceDialog::m_fr](#m_fr)|Структура, используемая для настройки `CFindReplaceDialog` объекта.|  
  
## <a name="remarks"></a>Примечания  
 В отличие от других общие диалоговые окна Windows `CFindReplaceDialog` объекты немодальное, что позволяет пользователям взаимодействовать с другими окнами, находясь на экране. Существует два типа из `CFindReplaceDialog` объектов: найти диалоговые окна и диалоговые окна поиска и замены. Несмотря на то, что диалоговые окна разрешить пользователю ввода поиска и поиска и замены строк, они не выполняют поиск и замена функции. Их необходимо добавить в приложение.  
  
 Для создания `CFindReplaceDialog` объекта, используйте предоставленный конструктор (который не имеет аргументов). Поскольку это немодального диалогового окна, выделение объектов в куче с помощью **новый** оператора, а не в стеке.  
  
 Один раз `CFindReplaceDialog` создается объект, необходимо вызвать [создать](#create) функции-члена для создания и отображения диалогового окна.  
  
 Используйте [m_fr](#m_fr) структуры для инициализации диалогового окна перед вызовом метода **создать**. `m_fr` Структуры имеет тип [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835). Дополнительные сведения о структуре см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Для родительского окна, уведомления запросов поиска и замены, вы должны использовать Windows [RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947) функции и использовать [ON_REGISTERED_MESSAGE](http://msdn.microsoft.com/library/93c1c068-ae8c-4e04-8a60-a603800ab57d) схемы сообщений макрос в окне фрейма, который обрабатывает это сообщение зарегистрированных.  
  
 Можно определить, является ли пользователь решил завершить диалогового окна с `IsTerminating` функции-члена.  
  
 `CFindReplaceDialog`зависит от COMMDLG. DLL-файл, поставляемый с Windows версии 3.1 и более поздней версии.  
  
 Чтобы настроить диалоговое окно, создайте класс, производный от `CFindReplaceDialog`, предоставить шаблон пользовательское диалоговое окно и добавить схемы сообщений для обработки сообщений уведомления из расширенных элементов управления. Все необработанные сообщения должны передаваться в базовый класс.  
  
 Настройка функцию-обработчик не является обязательным.  
  
 Дополнительные сведения об использовании `CFindReplaceDialog`, в разделе [классы общих диалоговых окон](../../mfc/common-dialog-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFindReplaceDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdlgs.h  
  
##  <a name="cfindreplacedialog"></a>CFindReplaceDialog::CFindReplaceDialog  
 Создает объект `CFindReplaceDialog`.  
  
```  
CFindReplaceDialog();
```  
  
### <a name="remarks"></a>Примечания  
 Поскольку `CFindReplaceDialog` представляет немодального диалогового окна, необходимо создать его в куче с помощью `new` оператор.  
  
 Во время удаления, предпринимает попытку выполнить `delete this` на указатель на окно. Если созданный диалоговым окном в стеке `this` указателя не существует и может привести к неопределенному поведению.  
  
 Дополнительные сведения о построении `CFindReplaceDialog` объектов, в разделе [диалоговое окно CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md) Обзор. Используйте [CFindReplaceDialog::Create](#create) функции-члена для отображения диалогового окна.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#170;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_1.cpp)]  
  
##  <a name="create"></a>CFindReplaceDialog::Create  
 Создает и отображает поиска или найти и заменить объект диалогового окна, в зависимости от значения `bFindDialogOnly`.  
  
```  
virtual BOOL Create(
    BOOL bFindDialogOnly,  
    LPCTSTR lpszFindWhat,  
    LPCTSTR lpszReplaceWith = NULL,  
    DWORD dwFlags = FR_DOWN,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `bFindDialogOnly`  
 Присвойте этому параметру значение `TRUE` для отображения **найти** диалоговое окно. Задайте для него значение `FALSE` для отображения **поиска и замены** диалоговое окно.  
  
 `lpszFindWhat`  
 Указатель на строку поиска по умолчанию в появившемся диалоговом окне. Если `NULL`, диалоговое окно не содержит строку поиска по умолчанию.  
  
 `lpszReplaceWith`  
 Указатель на строку замены по умолчанию, когда появится диалоговое окно. Если `NULL`, диалоговое окно не содержит строку замены по умолчанию.  
  
 `dwFlags`  
 Один или несколько флагов, которые можно использовать для настройки параметров диалогового окна, объединенные с помощью побитового оператора OR. Значение по умолчанию — `FR_DOWN`, который указывает, что поиск продолжать вниз. В разделе [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Дополнительные сведения об этих флагов.  
  
 `pParentWnd`  
 Указатель на окне родительский или владельца диалогового окна. Это окно, который получит специальное сообщение, указывающее, запрашивается действие поиска и замены. Если `NULL`, используется главного окна приложения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если объект диалогового окна был успешно создан; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Чтобы быть уведомления о запросах для поиска и замены родительского окна, необходимо использовать Windows [RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947) функция, возвращаемое значение является номер сообщения, уникальный для экземпляра приложения. Фрейма окна должны иметь элемент карты сообщений, в которой объявляется функция обратного вызова ( `OnFindReplace` в приведенном ниже примере), которая обрабатывает это зарегистрированный сообщение. В следующем фрагменте кода приведен пример того, как это сделать для класс фреймового окна с именем `CMyRichEditView`:  
  
 [!code-cpp[NVC_MFCDocView&#171;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_2.h)]  
  
 [!code-cpp[NVC_MFCDocView&#172;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#173;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_4.cpp)]  
  
 В рамках вашей `OnFindReplace` функции интерпретировать намерения пользователя с помощью [CFindReplaceDialog::FindNext](#findnext) и [CFindReplaceDialog::IsTerminating](#isterminating) методов и создание кода для операций поиска и замены.  
  
### <a name="example"></a>Пример  
  В примере показано [CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog).  
  
##  <a name="findnext"></a>CFindReplaceDialog::FindNext  
 Эта функция вызывается из функции обратного вызова для определения, является ли пользователь хочет найти следующее вхождение искомой строки.  
  
```  
BOOL FindNext() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если пользователю необходимо найти следующее вхождение искомой строки; в противном случае — 0.  
  
##  <a name="getfindstring"></a>CFindReplaceDialog::GetFindString  
 Эта функция вызывается из функции обратного вызова для получения строки по умолчанию для поиска.  
  
```  
CString GetFindString() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строка по умолчанию.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#69;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]  
  
##  <a name="getnotifier"></a>CFindReplaceDialog::GetNotifier  
 Эта функция вызывается для получения указателя на текущий поиск и замена диалоговым окном.  
  
```  
static CFindReplaceDialog* PASCAL GetNotifier(LPARAM lParam);
```  
  
### <a name="parameters"></a>Параметры  
 `lParam`  
 **Lparam** значение, передаваемое в фрейме окна **OnFindReplace** функции-члена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на текущее окно.  
  
### <a name="remarks"></a>Примечания  
 Он должен использоваться внутри функции обратного вызова для доступа к диалоговому окну текущего, вызвать его члена функции и доступ `m_fr` структуры.  
  
### <a name="example"></a>Пример  
 В разделе [CFindReplaceDialog::Create](#create) пример того, как зарегистрировать обработчик для получения уведомлений в диалоговом окне Поиск и замена OnFindReplace.  
  
 [!code-cpp[NVC_MFCDocView&#69;](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]  
  
##  <a name="getreplacestring"></a>CFindReplaceDialog::GetReplaceString  
 Эта функция вызывается для получения текущей строки замены.  
  
```  
CString GetReplaceString() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 По умолчанию строка, которой заменяется найденный строки.  
  
### <a name="example"></a>Пример  
  В примере показано [CFindReplaceDialog::GetFindString](#getfindstring).  
  
##  <a name="isterminating"></a>CFindReplaceDialog::IsTerminating  
 Вызов этой функции внутри функции обратного вызова для определения ли пользователь решил завершить диалоговое окно.  
  
```  
BOOL IsTerminating() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если пользователь решил завершить диалоговое окно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если эта функция возвращает ненулевое значение, необходимо вызвать `DestroyWindow` текущего диалогового, а любое диалоговое окно переменной указателя для функции-члена **NULL**. При необходимости можно также хранить последний введенный текст поиска и замены и использовать их для инициализации следующее окно поиска и замены.  
  
### <a name="example"></a>Пример  
  В примере показано [CFindReplaceDialog::GetFindString](#getfindstring).  
  
##  <a name="m_fr"></a>CFindReplaceDialog::m_fr  
 Используется для настройки `CFindReplaceDialog` объекта.  
  
```  
FINDREPLACE m_fr;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_fr`Структура типа [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835). Его члены хранить характеристики объекта диалоговых окон. После построения `CFindReplaceDialog` объекта, можно использовать `m_fr` для изменения различных значений в диалоговом окне.  
  
 Дополнительные сведения о структуре см. в разделе **FINDREPLACE** в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog).  
  
##  <a name="matchcase"></a>CFindReplaceDialog::MatchCase  
 Эта функция используется для определения, является ли пользователь хочет точно соответствовать регистру строки поиска.  
  
```  
BOOL MatchCase() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если пользователь желает найти вхождения строки поиска, точно соответствовать регистру строки поиска. в противном случае — 0.  
  
##  <a name="matchwholeword"></a>CFindReplaceDialog::MatchWholeWord  
 Эта функция вызывается для определения, хочет ли пользователь слова целиком.  
  
```  
BOOL MatchWholeWord() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если пользователю необходимо сопоставить только целые слова строки поиска. в противном случае — 0.  
  
##  <a name="replaceall"></a>CFindReplaceDialog::ReplaceAll  
 Эта функция вызывается для определения ли пользователю все вхождения строки замены.  
  
```  
BOOL ReplaceAll() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если пользователь запросил, чтобы заменить все строки, соответствующие строке замены; в противном случае — 0.  
  
##  <a name="replacecurrent"></a>CFindReplaceDialog::ReplaceCurrent  
 Эта функция вызывается для определения ли пользователю текущее слово для замены.  
  
```  
BOOL ReplaceCurrent() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если пользователь запросил заменяться что текущей выбранной строки в строку замены; в противном случае — 0.  
  
##  <a name="searchdown"></a>CFindReplaceDialog::SearchDown  
 Эта функция вызывается для определения, хочет ли пользователь поиска, чтобы перейти вниз.  
  
```  
BOOL SearchDown() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если пользователь хочет поиска для продолжения в направлении вниз; 0, если пользователь хочет поиска, чтобы перейти вверх.  
  
## <a name="see-also"></a>См. также  
 [Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)  

