---
title: "Класс CKeyboardManager | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CKeyboardManager
dev_langs:
- C++
helpviewer_keywords:
- CKeyboardManager class
ms.assetid: 4809ece6-89df-4479-8b53-9bf476ee107b
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: bbe12d2bf4af0008233df25e09f09008c402ee7f
ms.lasthandoff: 02/24/2017

---
# <a name="ckeyboardmanager-class"></a>Класс CKeyboardManager
Управляет таблицами клавиш быстрого доступа для окна главного и дочерних фреймов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CKeyboardManager : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CKeyboardManager::CKeyboardManager](#ckeyboardmanager)|Создает объект `CKeyboardManager`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CKeyboardManager::CleanUp](#cleanup)|Очищает ярлык ключа таблицы.|  
|[CKeyboardManager::FindDefaultAccelerator](#finddefaultaccelerator)|Получает сочетание клавиш по умолчанию для указанной команды и окна.|  
|[CKeyboardManager::IsKeyHandled](#iskeyhandled)|Определяет, обрабатывается ли ключ в таблице сочетаний клавиш.|  
|[CKeyboardManager::IsKeyPrintable](#iskeyprintable)|Указывает, является ли символ печатные.|  
|[CKeyboardManager::IsShowAllAccelerators](#isshowallaccelerators)|Указывает, является ли меню отображаются все сочетания клавиш для команды или сочетание клавиш по умолчанию.|  
|[CKeyboardManager::LoadState](#loadstate)|Загружает таблицы сочетания ключа из реестра Windows.|  
|[CKeyboardManager::ResetAll](#resetall)|Перезагружает таблиц сочетания ключа из ресурсов приложения.|  
|[CKeyboardManager::SaveState](#savestate)|Сохранение ярлыка ключа таблицы в реестр Windows.|  
|[CKeyboardManager::ShowAllAccelerators](#showallaccelerators)|Указывает, отображаются ли платформа сочетания клавиш для всех команд или к одному сочетанию клавиш для каждой команды. Этот метод не влияет на команды, которые имеют только один сочетанием клавиш.|  
|[CKeyboardManager::TranslateCharToUpper](#translatechartoupper)|Преобразует символ в его верхний регистр.|  
|[CKeyboardManager::UpdateAccelTable](#updateacceltable)|Обновляет таблицу ключа ярлык с новой таблицей ключа ярлык.|  
  
## <a name="remarks"></a>Примечания  
 Члены этого класса позволяют сохранить и загрузить сочетания ключей таблицы в реестр Windows, использовать шаблон для обновления таблиц ключа ярлык и поиск по умолчанию сочетание клавиш для команды в окне фрейма. Кроме того `CKeyboardManager` позволяет контролировать способ отображения сочетания клавиш для пользователя.  
  
 Не следует создавать `CKeyboardManager` объекта вручную. Он будет создан автоматически платформой приложения. Тем не менее, следует вызывать [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager) во время инициализации приложения. Чтобы получить указатель диспетчера клавиатуры для вашего приложения, вызовите [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager).  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как получить указатель на `CKeyboardManager` объекта из `CWinAppEx` , а также для отображения всех сочетаний клавиш, связанных с командами меню. Этот фрагмент кода является частью [пользовательские страницы образец](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages&#5;](../../mfc/reference/codesnippet/cpp/ckeyboardmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxkeyboardmanager.h  
  
##  <a name="a-nameckeyboardmanagera--ckeyboardmanagerckeyboardmanager"></a><a name="ckeyboardmanager"></a>CKeyboardManager::CKeyboardManager  
 Создает объект `CKeyboardManager`.  
  
```  
CKeyboardManager();
```  
  
### <a name="remarks"></a>Примечания  
 В большинстве случаев не нужно создавать `CKeyboardManager` напрямую. По умолчанию платформа создает его автоматически. Чтобы получить указатель на `CKeyboardManager`, вызовите [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager). При создании одной вручную, его необходимо инициализировать с помощью метода [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager).  
  
##  <a name="a-namecleanupa--ckeyboardmanagercleanup"></a><a name="cleanup"></a>CKeyboardManager::CleanUp  
 Освобождает `CKeyboardManager` ресурсы и очищает все сопоставлений сочетаний клавиш.  
  
```  
static void CleanUp();
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о сочетаниях клавиш см. в разделе [Настройка мыши и клавиатуры](../../mfc/keyboard-and-mouse-customization.md).  
  
 Эта функция вызывается, когда приложение завершает работу, так как платформа вызывает функцию его автоматически во время выхода приложения нет.  
  
##  <a name="a-namefinddefaultacceleratora--ckeyboardmanagerfinddefaultaccelerator"></a><a name="finddefaultaccelerator"></a>CKeyboardManager::FindDefaultAccelerator  
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
 Указатель фрейма окна.  
  
 [in] `bIsDefaultFrame`  
 Указывает, является ли фрейме окна фрейма окна по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если найден ярлык; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод выполняет поиск по указанной команды `uiCmd` и получает сочетание клавиш по умолчанию. Затем этот метод принимает строку, связанную с этого сочетания клавиш и записывает значение `str` параметр.  
  
##  <a name="a-nameiskeyhandleda--ckeyboardmanageriskeyhandled"></a><a name="iskeyhandled"></a>CKeyboardManager::IsKeyHandled  
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
|[in] `fVirt`|Задает поведение клавиш. Список возможных значений см. в разделе [УСКОРЕНИЕ структуры](http://msdn.microsoft.com/library/windows/desktop/ms646340).|  
|[in] `pWndFrame`|Рамка окна. Этот метод определяет, обрабатывается ли сочетания клавиш в этом кадре.|  
|[in] `bIsDefaultFrame`|Логический параметр, указывающий ли `pWndFrame` является фрейме окна по умолчанию.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если сочетание клавиш обрабатывается. `FALSE`Если ключ не обрабатывается или `pWndFrame` — `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Входные параметры должны соответствовать записи в таблице сочетаний клавиш как для `nKey` и `fVirt` для определения того, обрабатывается ли сочетания клавиш в `pWndFrame`.  
  
##  <a name="a-nameiskeyprintablea--ckeyboardmanageriskeyprintable"></a><a name="iskeyprintable"></a>CKeyboardManager::IsKeyPrintable  
 Указывает, является ли символ печатные.  
  
```  
static BOOL __stdcall IsKeyPrintable(const UINT nChar);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `nChar`|Символ, который проверяет этот метод.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если печатный символ нуль, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Этот метод не выполняется, если вызов [GetKeyboardState](http://msdn.microsoft.com/library/windows/desktop/ms646299) завершается ошибкой.  
  
##  <a name="a-nameisshowallacceleratorsa--ckeyboardmanagerisshowallaccelerators"></a><a name="isshowallaccelerators"></a>CKeyboardManager::IsShowAllAccelerators  
 Указывает, отображать ли меню, сочетания клавиш, связанные с командами меню или сочетания клавиш по умолчанию.  
  
```  
static BOOL IsShowAllAccelerators();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если приложение перечислены сочетания клавиш для команд меню; 0, если приложение отображает только сочетания клавиш по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Приложение перечислены сочетания клавиш для команды меню в строке меню. Используйте функцию [CKeyboardManager::ShowAllAccelerators](#showallaccelerators) для управления ли приложение выводит список всех сочетаний клавиш или только сочетания клавиш по умолчанию.  
  
##  <a name="a-nameloadstatea--ckeyboardmanagerloadstate"></a><a name="loadstate"></a>CKeyboardManager::LoadState  
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
 Указатель фрейма окна для использования в качестве стандартного окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если состояние успешно загружен или 0 в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Если `lpszProfileName` параметр `NULL`, этот метод проверяет расположение реестра по умолчанию для `CKeyboardManager` данных. В разделе реестра по умолчанию определяется [CWinAppEx Class](../../mfc/reference/cwinappex-class.md). Данные должны записываться ранее с помощью метода [CKeyboardManager::SaveState](#savestate).  
  
 Если окно по умолчанию не задан, будет использоваться фрейма главного окна приложения.  
  
##  <a name="a-nameresetalla--ckeyboardmanagerresetall"></a><a name="resetall"></a>CKeyboardManager::ResetAll  
 Перезагружает таблиц сочетания ключа из ресурсов приложения.  
  
```  
void ResetAll();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция удаляет ярлыки, хранящиеся в `CKeyboardManager` экземпляра. Затем он перезагрузит состояние диспетчера клавиатуры из ресурсов приложения.  
  
##  <a name="a-namesavestatea--ckeyboardmanagersavestate"></a><a name="savestate"></a>CKeyboardManager::SaveState  
 Сохранение ярлыка ключа таблицы в реестр Windows.  
  
```  
BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Путь в реестре для сохранения `CKeyboardManager` состояния.  
  
 [in] `pDefaultFrame`  
 Указатель фрейма окна, которая становится окна по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если диспетчер состояния клавиатуры сохранен успешно, или 0 в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Если `lpszProfileName` параметр `NULL`, этот метод запишет `CKeyboardManager` состояния в расположение по умолчанию, определяемое [CWinAppEx Class](../../mfc/reference/cwinappex-class.md). Если указать расположение, можно загрузить данные позже с помощью метода [CKeyboardManager::LoadState](#loadstate).  
  
 Если окно по умолчанию не указано, как окна по умолчанию будет использоваться фрейма главного окна.  
  
##  <a name="a-nameshowallacceleratorsa--ckeyboardmanagershowallaccelerators"></a><a name="showallaccelerators"></a>CKeyboardManager::ShowAllAccelerators  
 Показывает все сочетания клавиш, связанные с командами меню.  
  
```  
static void ShowAllAccelerators(
    BOOL bShowAll = TRUE,  
    LPCTSTR lpszDelimiter = _afxDefaultAcceleratorDelimiter);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bShowAll`  
 Если `true`, отображаются все сочетания клавиш. Если `false`, будет отображаться только первый сочетание клавиш.  
  
 [in] `lpszDelimiter`  
 Строка, вставляемая между сочетания клавиш. Этот разделитель не оказывает влияния только одно сочетание клавиш отображается.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию Если команда имеет более одного сочетание клавиш, связанное с ним, только первый клавиш будут показаны. Эта функция позволяет перечислять все сочетания клавиш, связанных с всех команд.  
  
 Сочетания клавиш отображается рядом с командой в строке меню. Если отображаются все сочетания клавиш, предоставляемые строка `lpszDelimiter` разделения отдельных сочетания клавиш.  
  
##  <a name="a-nametranslatechartouppera--ckeyboardmanagertranslatechartoupper"></a><a name="translatechartoupper"></a>CKeyboardManager::TranslateCharToUpper  
 Преобразует символ в его верхний регистр.  
  
```  
static UINT TranslateCharToUpper(const UINT nChar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nChar`  
 Символ для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Символ, который представляет верхнем регистре входного параметра.  
  
##  <a name="a-nameupdateacceltablea--ckeyboardmanagerupdateacceltable"></a><a name="updateacceltable"></a>CKeyboardManager::UpdateAccelTable  
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
 Размер новой таблицы ярлык.  
  
 [in] `pDefaultFrame`  
 Указатель фрейма окна по умолчанию.  
  
 [in] `hAccelNew`  
 Дескриптор в новую таблицу ярлык.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно используйте для замены существующей таблицы ярлык новые сочетания клавиш для нескольких объектов окна фрейма. Функция получает шаблон документа в качестве параметра для получения доступа ко всем объектам окна фрейма, подключен к шаблона данного документа.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)   
 [Настройка мыши и клавиатуры](../../mfc/keyboard-and-mouse-customization.md)




