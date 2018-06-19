---
title: Класс CKeyboardManager | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CleanUp
- AFXKEYBOARDMANAGER/CKeyboardManager::FindDefaultAccelerator
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyHandled
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyPrintable
- AFXKEYBOARDMANAGER/CKeyboardManager::IsShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::LoadState
- AFXKEYBOARDMANAGER/CKeyboardManager::ResetAll
- AFXKEYBOARDMANAGER/CKeyboardManager::SaveState
- AFXKEYBOARDMANAGER/CKeyboardManager::ShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::TranslateCharToUpper
- AFXKEYBOARDMANAGER/CKeyboardManager::UpdateAccelTable
dev_langs:
- C++
helpviewer_keywords:
- CKeyboardManager [MFC], CKeyboardManager
- CKeyboardManager [MFC], CleanUp
- CKeyboardManager [MFC], FindDefaultAccelerator
- CKeyboardManager [MFC], IsKeyHandled
- CKeyboardManager [MFC], IsKeyPrintable
- CKeyboardManager [MFC], IsShowAllAccelerators
- CKeyboardManager [MFC], LoadState
- CKeyboardManager [MFC], ResetAll
- CKeyboardManager [MFC], SaveState
- CKeyboardManager [MFC], ShowAllAccelerators
- CKeyboardManager [MFC], TranslateCharToUpper
- CKeyboardManager [MFC], UpdateAccelTable
ms.assetid: 4809ece6-89df-4479-8b53-9bf476ee107b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b9d4aace502310836429ec8f8f9db74d7cf17ff
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369106"
---
# <a name="ckeyboardmanager-class"></a>Класс CKeyboardManager
Управляет таблицами клавиш быстрого доступа для окна главного и дочерних фреймов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CKeyboardManager : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CKeyboardManager::CKeyboardManager](#ckeyboardmanager)|Создает объект `CKeyboardManager`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CKeyboardManager::CleanUp](#cleanup)|Очистка таблиц ключа ярлык.|  
|[CKeyboardManager::FindDefaultAccelerator](#finddefaultaccelerator)|Получает сочетание клавиш по умолчанию для указанной команды и окна.|  
|[CKeyboardManager::IsKeyHandled](#iskeyhandled)|Определяет, обрабатывается ли ключ в таблице сочетаний клавиш.|  
|[CKeyboardManager::IsKeyPrintable](#iskeyprintable)|Указывает, является ли символ печати.|  
|[CKeyboardManager::IsShowAllAccelerators](#isshowallaccelerators)|Указывает, является ли меню отображаются все сочетания клавиш для команды или сочетание клавиш по умолчанию.|  
|[CKeyboardManager::LoadState](#loadstate)|Загружает таблицы сочетания ключа из реестра Windows.|  
|[CKeyboardManager::ResetAll](#resetall)|Перезагружает таблиц сочетания ключа из ресурсов приложения.|  
|[CKeyboardManager::SaveState](#savestate)|Сохранение ярлыка таблиц ключа реестра Windows.|  
|[CKeyboardManager::ShowAllAccelerators](#showallaccelerators)|Указывает, отображаются ли платформа сочетания клавиш для всех команд или одного сочетания клавиш для каждой команды. Этот метод не влияет на команды, которые имеют только один сочетанием клавиш.|  
|[CKeyboardManager::TranslateCharToUpper](#translatechartoupper)|Преобразует символ в его верхний регистр.|  
|[CKeyboardManager::UpdateAccelTable](#updateacceltable)|Обновляет таблицу ключа ярлык с новой таблицей ключа ярлык.|  
  
## <a name="remarks"></a>Примечания  
 Члены этого класса позволяют сохранить и загрузить таблиц ключа ярлык в реестре Windows, используйте шаблон для обновления таблиц ключа ярлык и найти сочетание клавиш по умолчанию для команды в окне фрейма. Кроме того `CKeyboardManager` объекта позволяет управлять отображением сочетания клавиш для пользователя.  
  
 Не следует создавать `CKeyboardManager` объекта вручную. Он будет создан автоматически платформой приложения. Тем не менее, необходимо вызвать [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager) во время инициализации приложения. Чтобы получить указатель к диспетчеру клавиатуры для вашего приложения, вызовите [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как получить указатель на `CKeyboardManager` объекта из `CWinAppEx` , а также для отображения всех сочетаний клавиш, связанных с помощью команд меню. Этот фрагмент кода является частью [образец пользовательские страницы](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages#5](../../mfc/reference/codesnippet/cpp/ckeyboardmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxkeyboardmanager.h  
  
##  <a name="ckeyboardmanager"></a>  CKeyboardManager::CKeyboardManager  
 Создает объект `CKeyboardManager`.  
  
```  
CKeyboardManager();
```  
  
### <a name="remarks"></a>Примечания  
 В большинстве случаев не нужно создавать `CKeyboardManager` напрямую. По умолчанию платформа создает ее автоматически. Чтобы получить указатель на `CKeyboardManager`, вызовите [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager). Если сделать это вручную, его необходимо инициализировать с помощью метода [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager).  
  
##  <a name="cleanup"></a>  CKeyboardManager::CleanUp  
 Освобождает `CKeyboardManager` ресурсы и не удалит все сопоставлений сочетаний клавиш.  
  
```  
static void CleanUp();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о сочетаниях клавиш см. в разделе [Настройка мыши и клавиатуры](../../mfc/keyboard-and-mouse-customization.md).  
  
 Эта функция вызывается, когда приложение завершает работу, так как платформа вызывает функцию его автоматически во время выхода приложения нет.  
  
##  <a name="finddefaultaccelerator"></a>  CKeyboardManager::FindDefaultAccelerator  
 Получает сочетание клавиш по умолчанию для указанной команды и окна.  
  
```  
static BOOL FindDefaultAccelerator(
    UINT uiCmd,  
    CString& str,  
    CFrameWnd* pWndFrame,  
    BOOL bIsDefaultFrame);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmd`  
 Идентификатор команды.  
  
 [выходной] `str`  
 Ссылка на объект `CString`.  
  
 [in] `pWndFrame`  
 Указатель на фрейм окна.  
  
 [in] `bIsDefaultFrame`  
 Указывает, является ли окно фрейма окна фрейма по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если найден ярлык; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод выполняет поиск команду, указанную параметром `uiCmd` и получает сочетание клавиш по умолчанию. Затем этот метод принимает строку, связанную с этого сочетания клавиш и записывает значение `str` параметра.  
  
##  <a name="iskeyhandled"></a>  CKeyboardManager::IsKeyHandled  
 Определяет, обрабатывается ли указанный ключ [CKeyboardManager класса](../../mfc/reference/ckeyboardmanager-class.md).  
  
```  
static BOOL __stdcall IsKeyHandled(
    WORD nKey,  
    BYTE fVirt,  
    CFrameWnd* pWndFrame,  
    BOOL bIsDefaultFrame);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `nKey`|Проверяемый ключ.|  
|[in] `fVirt`|Задает поведение сочетания клавиш. Список возможных значений см. в разделе [УСКОРЕНИЕ структуры](http://msdn.microsoft.com/library/windows/desktop/ms646340).|  
|[in] `pWndFrame`|Окна фрейма. Этот метод определяет, обрабатывается ли сочетания клавиш в этом кадре.|  
|[in] `bIsDefaultFrame`|Логический параметр, указывает ли `pWndFrame` – окно рамки по умолчанию.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если сочетание клавиш обрабатывается. `FALSE` Если ключ еще не обработаны или `pWndFrame` — `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Входные параметры должна совпадать с записью в таблице сочетаний клавиш как для `nKey` и `fVirt` для определения того, обрабатывается ли сочетания клавиш в `pWndFrame`.  
  
##  <a name="iskeyprintable"></a>  CKeyboardManager::IsKeyPrintable  
 Указывает, является ли символ печати.  
  
```  
static BOOL __stdcall IsKeyPrintable(const UINT nChar);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `nChar`|Символ, который проверяет, этот метод.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если печатный символ, нуль, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Этот метод завершается ошибкой, если вызов [GetKeyboardState](http://msdn.microsoft.com/library/windows/desktop/ms646299) завершается ошибкой.  
  
##  <a name="isshowallaccelerators"></a>  CKeyboardManager::IsShowAllAccelerators  
 Указывает, является ли меню отображаются все сочетания клавиш, связанных с помощью команд меню или сочетания клавиш по умолчанию.  
  
```  
static BOOL IsShowAllAccelerators();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если приложение перечислены сочетания клавиш для команд меню; 0, если приложение отображает только сочетания клавиш по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Приложение перечислены сочетания клавиш для команды меню в строке меню. Используйте функцию [CKeyboardManager::ShowAllAccelerators](#showallaccelerators) для управления ли приложение выводит список всех сочетаний клавиш или просто сочетания клавиш по умолчанию.  
  
##  <a name="loadstate"></a>  CKeyboardManager::LoadState  
 Загружает таблицы сочетания ключа из реестра Windows.  
  
```  
BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Путь реестра где `CKeyboardManager` данные сохраняются.  
  
 [in] `pDefaultFrame`  
 Указатель на окно фрейма для использования в качестве окна по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если состояние, к которому был успешно загружен или 0 в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Если `lpszProfileName` параметр `NULL`, этот метод выполняет проверку реестра по умолчанию для `CKeyboardManager` данных. Расположение реестра по умолчанию указывается [CWinAppEx класс](../../mfc/reference/cwinappex-class.md). Данные должны записываться ранее с помощью метода [CKeyboardManager::SaveState](#savestate).  
  
 Если окна по умолчанию не указан, будет использоваться фрейма главного окна приложения.  
  
##  <a name="resetall"></a>  CKeyboardManager::ResetAll  
 Перезагружает таблиц сочетания ключа из ресурсов приложения.  
  
```  
void ResetAll();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция очищает сочетания клавиш, хранящиеся в `CKeyboardManager` экземпляра. Затем он перезагрузит состояние диспетчера клавиатуры из ресурсов приложения.  
  
##  <a name="savestate"></a>  CKeyboardManager::SaveState  
 Сохранение ярлыка таблиц ключа реестра Windows.  
  
```  
BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Путь реестра для сохранения `CKeyboardManager` состояния.  
  
 [in] `pDefaultFrame`  
 Указатель на окно фрейма, который становится окна по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если диспетчер состояния клавиатуры был сохранен успешно, или 0 в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Если `lpszProfileName` параметр `NULL`, этот метод осуществляет запись `CKeyboardManager` состояние по умолчанию местоположении, заданном свойством [CWinAppEx класс](../../mfc/reference/cwinappex-class.md). Если расположение указано, можно загрузить данные позже с помощью метода [CKeyboardManager::LoadState](#loadstate).  
  
 Если окна по умолчанию не задан, как окна по умолчанию будет использоваться фрейма главного окна.  
  
##  <a name="showallaccelerators"></a>  CKeyboardManager::ShowAllAccelerators  
 Показывает все сочетания клавиш, связанных с помощью команд меню.  
  
```  
static void ShowAllAccelerators(
    BOOL bShowAll = TRUE,  
    LPCTSTR lpszDelimiter = _afxDefaultAcceleratorDelimiter);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bShowAll`  
 Если `true`, отображаются все сочетания клавиш. Если `false`, будет отображаться только первый сочетание клавиш.  
  
 [in] `lpszDelimiter`  
 Строка, вставляемая между сочетания клавиш. Этот разделитель имеет смысл, если только одно сочетание клавиш отображаться.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию Если команда имеет более одного сочетание клавиш, связанное с ним, только первый ключ ярлык будет отображен. Эта функция позволяет перечислять все сочетания клавиш, связанных с все команды.  
  
 Рядом с командой в строке меню будут перечислены сочетания клавиш. Если отображаются все сочетания клавиш, строки, предоставляемые `lpszDelimiter` между отдельными сочетания клавиш.  
  
##  <a name="translatechartoupper"></a>  CKeyboardManager::TranslateCharToUpper  
 Преобразует символ в его верхний регистр.  
  
```  
static UINT TranslateCharToUpper(const UINT nChar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nChar`  
 Символ для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Символ верхнего регистра входного параметра.  
  
##  <a name="updateacceltable"></a>  CKeyboardManager::UpdateAccelTable  
 Обновляет таблицу ключа ярлык с новой таблицей ключа ярлык.  
  
```  
BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,  
    LPACCEL lpAccel,  
    int nSize,  
    CFrameWnd* pDefaultFrame = NULL);

 
BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,  
    HACCEL hAccelNew,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pTemplate`  
 Указатель на шаблон документа.  
  
 [in] `lpAccel`  
 Указатель на новое сочетание клавиш.  
  
 [in] `nSize`  
 Размер в новую таблицу ярлык.  
  
 [in] `pDefaultFrame`  
 Указатель на фрейм окна по умолчанию.  
  
 [in] `hAccelNew`  
 Дескриптор в новую таблицу ярлык.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для замены существующей таблицы контекстное новые сочетания клавиш для нескольких объектов окна фрейма. Функция получает шаблон документа в качестве параметра для получения доступа ко всем объектам окна фрейма, подключенных к шаблону данного документа.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)   
 [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)   
 [Настройка мыши и клавиатуры](../../mfc/keyboard-and-mouse-customization.md)



