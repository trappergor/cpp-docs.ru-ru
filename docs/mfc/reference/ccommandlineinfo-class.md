---
title: "Класс CCommandLineInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCommandLineInfo
- AFXWIN/CCommandLineInfo
- AFXWIN/CCommandLineInfo::CCommandLineInfo
- AFXWIN/CCommandLineInfo::ParseParam
- AFXWIN/CCommandLineInfo::m_bRunAutomated
- AFXWIN/CCommandLineInfo::m_bRunEmbedded
- AFXWIN/CCommandLineInfo::m_bShowSplash
- AFXWIN/CCommandLineInfo::m_nShellCommand
- AFXWIN/CCommandLineInfo::m_strDriverName
- AFXWIN/CCommandLineInfo::m_strFileName
- AFXWIN/CCommandLineInfo::m_strPortName
- AFXWIN/CCommandLineInfo::m_strPrinterName
- AFXWIN/CCommandLineInfo::m_strRestartIdentifier
dev_langs:
- C++
helpviewer_keywords:
- CCommandLineInfo class
- command line, parsing
- parsing, command-line arguments
- argv argument
- startup code, parsing command-line arguments
- application flags [C++]
ms.assetid: 3e313ddb-0a82-4991-87ac-a27feff4668c
caps.latest.revision: 21
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
ms.openlocfilehash: cb8cd58e4e7cf0318b8826cf473739e26e730273
ms.lasthandoff: 02/24/2017

---
# <a name="ccommandlineinfo-class"></a>Класс CCommandLineInfo
Помогает в синтаксическом разборе командной строки при запуске приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CCommandLineInfo : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCommandLineInfo::CCommandLineInfo](#ccommandlineinfo)|Создает значение по умолчанию `CCommandLineInfo` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCommandLineInfo::ParseParam](#parseparam)|Переопределите этот обратный вызов для анализа отдельных параметров.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCommandLineInfo::m_bRunAutomated](#m_brunautomated)|Указывает командной строки **/Automation** обнаружен параметр.|  
|[CCommandLineInfo::m_bRunEmbedded](#m_brunembedded)|Указывает командной строки **и внедрение** обнаружен параметр.|  
|[CCommandLineInfo::m_bShowSplash](#m_bshowsplash)|Указывает, должен ли отображаться экран-заставку.|  
|[CCommandLineInfo::m_nShellCommand](#m_nshellcommand)|Указывает команду оболочки для обработки.|  
|[CCommandLineInfo::m_strDriverName](#m_strdrivername)|Указывает драйверу имя, если команда shell — печати; в противном случае — пустой.|  
|[CCommandLineInfo::m_strFileName](#m_strfilename)|Указывает имя файла, который требуется открыть или печати; пустой, если создать или DDE командной оболочки.|  
|[CCommandLineInfo::m_strPortName](#m_strportname)|Указывает порт имя, если команда shell — печати; в противном случае — пустой.|  
|[CCommandLineInfo::m_strPrinterName](#m_strprintername)|Указывает принтер имя, если команда shell — печати; в противном случае — пустой.|  
|[CCommandLineInfo::m_strRestartIdentifier](#m_strrestartidentifier)|Указывает перезапуска уникальный идентификатор диспетчера перезапуска, если диспетчер перезапуска перезапуска приложения.|  
  
## <a name="remarks"></a>Примечания  
 MFC-приложении обычно создается локальный экземпляр этого класса в [InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) функция объекта приложения. Затем этот объект передается в [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline), многократно вызывает [ParseParam](#parseparam) для заполнения `CCommandLineInfo` объекта. `CCommandLineInfo` Объект затем передается [CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand) для обработки аргументов командной строки и флаги.  
  
 Этот объект можно использовать для инкапсуляции следующие параметры командной строки и параметры:  
  
|Аргумент командной строки|Команда, выполняемая|  
|----------------------------|----------------------|  
|*app*|Новый файл.|  
|*приложение* имя файла|Открытие файла.|  
|*приложение* **/p** имя файла|Печать файла на принтер по умолчанию.|  
|*приложение* **/pt** filename порт драйвера принтера|Печать файла на указанный принтер.|  
|*app* **/dde**|Запустите и await команд DDE.|  
|*приложение*  ** /Automation**|Запустить как сервер OLE-автоматизации.|  
|*приложение* **и внедрение**|Запустите изменение встроенного элемента OLE.|  
|*приложение*  ** /Register**<br /><br /> *приложение*  ** /regserver**|Информирует приложение для выполнения любых задач регистрации.|  
|*приложение* **/ Unregister**<br /><br /> *приложение* **/Unregserver**|Информирует приложение для выполнения любых задач отмены регистрации.|  
  
 Наследовать новый класс из `CCommandLineInfo` обрабатывать другие флаги и значения параметров. Переопределение [ParseParam](#parseparam) для обработки новых флагов.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CCommandLineInfo`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="ccommandlineinfo"></a>CCommandLineInfo::CCommandLineInfo  
 Этот конструктор создает `CCommandLineInfo` объектов со значениями по умолчанию.  
  
```  
CCommandLineInfo();
```  
  
### <a name="remarks"></a>Примечания  
 Значение по умолчанию — для отображения экрана-заставки ( `m_bShowSplash` **= TRUE**) и для выполнения этой команды в меню File ( `m_nShellCommand` **= Создатьфайл**).  
  
 Приложение вызывает framework [ParseParam](#parseparam) для заполнения элементов данных этого объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#54;](../../mfc/codesnippet/cpp/ccommandlineinfo-class_1.cpp)]  
  
##  <a name="m_brunautomated"></a>CCommandLineInfo::m_bRunAutomated  
 Указывает, что **/Automation** флаг был найден в командной строке.  
  
```  
BOOL m_bRunAutomated;  
```  
  
### <a name="remarks"></a>Примечания  
 Если **TRUE**, это означает, что запущен как сервер OLE-автоматизации.  
  
##  <a name="m_brunembedded"></a>CCommandLineInfo::m_bRunEmbedded  
 Указывает, что **и внедрение** флаг был найден в командной строке.  
  
```  
BOOL m_bRunEmbedded;  
```  
  
### <a name="remarks"></a>Примечания  
 Если **TRUE**, это означает, что запущен для редактирования встроенного элемента OLE.  
  
##  <a name="m_bshowsplash"></a>CCommandLineInfo::m_bShowSplash  
 Задает отображение экрана-заставки.  
  
```  
BOOL m_bShowSplash;  
```  
  
### <a name="remarks"></a>Примечания  
 Если **TRUE**, это означает экран-заставку для этого приложения должен отображаться во время запуска. Реализация по умолчанию [ParseParam](#parseparam) устанавливает этот элемент данных **TRUE** Если [m_nShellCommand](#m_nshellcommand) равен **CCommandLineInfo::FileNew**.  
  
##  <a name="m_nshellcommand"></a>CCommandLineInfo::m_nShellCommand  
 Указывает команду оболочки для этого экземпляра приложения.  
  
```  
m_nShellCommand;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип для этого элемента данных является следующий тип перечисления, который определен в `CCommandLineInfo` класса.  
  
 `enum{`  
  
 `FileNew,`  
  
 `FileOpen,`  
  
 `FilePrint,`  
  
 `FilePrintTo,`  
  
 `FileDDE,`  
  
 `AppRegister,`  
  
 `AppUnregister,`  
  
 `RestartByRestartManager,`  
  
 `FileNothing = -1`  
  
 `};`  
  
 Краткое описание этих значений см.  
  
- `CCommandLineInfo::FileNew`Указывает, что имя файла не было найдено в командной строке.  
  
- `CCommandLineInfo::FileOpen`Указывает, что имя файла было найдено в командной строке, и что ни один из флагов не найдены в командной строке: `/p`, `/pt`, `/dde`.  
  
- `CCommandLineInfo::FilePrint`Указывает, что `/p` флаг был найден в командной строке.  
  
- `CCommandLineInfo::FilePrintTo`Указывает, что `/pt` флаг был найден в командной строке.  
  
- `CCommandLineInfo::FileDDE`Указывает, что `/dde` флаг был найден в командной строке.  
  
- `CCommandLineInfo::AppRegister`Указывает, что `/Register` или `/Regserver` флаг был найден в командной строке и попросили зарегистрировать приложение.  
  
- `CCommandLineInfo::AppUnregister`Указывает, что `/Unregister` или `/Unregserver` приложения получил запрос на регистрацию.  
  
- `CCommandLineInfo::RestartByRestartManager`Указывает, что приложение была перезапущена диспетчером перезапуска.  
  
- `CCommandLineInfo::FileNothing`Отключает отображение нового дочернего окна MDI при запуске. По умолчанию при запуске приложения MDI, создаваемые мастером приложений отображается нового дочернего окна. Чтобы отключить эту функцию, приложение может использовать `CCommandLineInfo::FileNothing` как при вызове команды shell [ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand). `ProcessShellCommand`вызывается методом `InitInstance( )` всех `CWinApp` производных классов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#55;](../../mfc/codesnippet/cpp/ccommandlineinfo-class_2.cpp)]  
  
##  <a name="m_strdrivername"></a>CCommandLineInfo::m_strDriverName  
 Сохраняет значение третьего параметра без флага в командной строке.  
  
```  
CString m_strDriverName;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот параметр обычно является имя драйвера принтера для печати на команду оболочки. Реализация по умолчанию [ParseParam](#parseparam) задает этот только если член данных **/pt** флаг был найден в командной строке.  
  
##  <a name="m_strfilename"></a>CCommandLineInfo::m_strFileName  
 Сохраняет значение первого параметра без флага в командной строке.  
  
```  
CString m_strFileName;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот параметр обычно является имя открываемого файла.  
  
##  <a name="m_strportname"></a>CCommandLineInfo::m_strPortName  
 Сохраняет значение без флага четвертый параметр в командной строке.  
  
```  
CString m_strPortName;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот параметр обычно является имя порта принтера для печати на команду оболочки. Реализация по умолчанию [ParseParam](#parseparam) задает этот только если член данных **/pt** флаг был найден в командной строке.  
  
##  <a name="m_strprintername"></a>CCommandLineInfo::m_strPrinterName  
 Сохраняет значение второго параметра без флага в командной строке.  
  
```  
CString m_strPrinterName;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот параметр обычно является имя принтера для печати на команду оболочки. Реализация по умолчанию [ParseParam](#parseparam) задает этот только если член данных **/pt** флаг был найден в командной строке.  
  
##  <a name="m_strrestartidentifier"></a>CCommandLineInfo::m_strRestartIdentifier  
 Уникальный перезапустите идентификатор в командной строке.  
  
```  
CString m_strRestartIdentifier;  
```  
  
### <a name="remarks"></a>Примечания  
 Перезапуск идентификатор является уникальным для каждого экземпляра приложения.  
  
 Если диспетчер перезапуска завершает работу приложения и настройки его диспетчер перезапуска выполняет приложение из командной строки с идентификатором перезапуска как необязательный параметр. Когда диспетчер перезапуска использует идентификатор перезапуска, приложение можно открыть ранее открытые документы и восстанавливать файлы автоматически сохраненная.  
  
##  <a name="parseparam"></a>CCommandLineInfo::ParseParam  
 Платформа вызывает эту функцию для синтаксического анализа и интерпретации отдельных параметров из командной строки. Вторая версия отличается от первого только в проектах Юникода.  
  
```  
virtual void ParseParam(
    const char* pszParam,  
    BOOL bFlag,  
    BOOL bLast);

 
virtual void ParseParam(
    const TCHAR* pszParam,  
    BOOL bFlag,  
    BOOL bLast);
```  
  
### <a name="parameters"></a>Параметры  
 `pszParam`  
 Параметр или флаг.  
  
 *bFlag*  
 Указывает, является ли `pszParam` параметр или флаг.  
  
 `bLast`  
 Указывает, является ли это последний параметр или флаг в командной строке.  
  
### <a name="remarks"></a>Примечания  
 [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline) вызовов `ParseParam` один раз для каждого параметра или флаг в командной строке, передав аргумент `pszParam`. Если первый символ параметра " ** - **«или» ** / **", то он удаляется и *bFlag* задано значение **TRUE**. При синтаксическом анализе последний параметр, `bLast` равен **TRUE**.  
  
 Реализация по умолчанию эта функция распознает следующие флаги: **/p**, **/pt**, **/dde**, **/Automation**, и **и внедрение**, как показано в следующей таблице:  
  
|Аргумент командной строки|Команда, выполняемая|  
|----------------------------|----------------------|  
|*app*|Новый файл.|  
|*приложение* имя файла|Открытие файла.|  
|*приложение* **/p** имя файла|Печать файла на принтер по умолчанию.|  
|*приложение* **/pt** filename порт драйвера принтера|Печать файла на указанный принтер.|  
|*app* **/dde**|Запустите и await команд DDE.|  
|*приложение*  ** /Automation**|Запустить как сервер OLE-автоматизации.|  
|*приложение* **и внедрение**|Запустите изменение встроенного элемента OLE.|  
|*приложение*  ** /Register**<br /><br /> *приложение*  ** /regserver**|Информирует приложение для выполнения любых задач регистрации.|  
|*приложение* **/ Unregister**<br /><br /> *приложение* **/Unregserver**|Информирует приложение для выполнения любых задач отмены регистрации.|  
  
 Эти сведения хранятся в [m_bRunAutomated](#m_brunautomated), [m_bRunEmbedded](#m_brunembedded), и [m_nShellCommand](#m_nshellcommand). Флаги помечены либо прямой косой черты " ** / **«или дефиса» ** - **".  
  
 Реализация по умолчанию помещается в первый параметр без флага [m_strFileName](#m_strfilename). В случае использования **/pt** флаг, реализация по умолчанию помещает второй, третий и четвертый параметры без флага в [m_strPrinterName](#m_strprintername), [m_strDriverName](#m_strdrivername), и [m_strPortName](#m_strportname)соответственно.  
  
 Реализация по умолчанию также устанавливает [m_bShowSplash](#m_bshowsplash) для **TRUE** только в случае нового файла. В случае файл нового пользователя вступила в действие с участием самого приложения. Во всех остальных случаях, включая Открытие существующих файлов с помощью оболочки действия пользователя включает в себя файл напрямую. В документе зрения экран-заставка не требуется объявить о запуске приложения.  
  
 Переопределите эту функцию в производном классе для обработки других флага и значения параметров.  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)   
 [CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)


