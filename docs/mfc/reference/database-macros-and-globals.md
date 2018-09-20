---
title: Макросы и глобальные объекты базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFXDB/AFX_ODBC_CALL
- AFXDB/AFX_SQL_ASYNC
- AFXDB/AFX_SQL_SYNC
- AFXDB/AfxGetHENV
dev_langs:
- C++
helpviewer_keywords:
- global database functions [MFC]
- database macros [MFC]
- database globals [MFC]
- global functions [MFC], database functions
- macros [MFC], MFC database
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 67a0fd2af9bb8bf3ec11d5a4e2a38c195b18633c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424252"
---
# <a name="database-macros-and-globals"></a>Макросы и глобальные объекты баз данных

Макросы и глобальные объекты, перечисленные ниже применяются к приложениям баз данных на основе ODBC. Они не используются с приложениями на основе DAO.

Прежде чем 4.2 MFC, макросы `AFX_SQL_ASYNC` и `AFX_SQL_SYNC` дал возможность дать время для других процессов асинхронных операций. Начиная с MFC версии 4.2, реализация этих макросов, изменить, так как классы MFC ODBC, используемые только синхронные операции. Макрос `AFX_ODBC_CALL` были знакомы с MFC версии 4.2.

### <a name="database-macros"></a>Макросы базы данных

|||
|-|-|
|[AFX_ODBC_CALL](#afx_odbc_call)|Вызывает функцию ODBC API, который возвращает `SQL_STILL_EXECUTING`. `AFX_ODBC_CALL` будет повторно вызывать функцию до его больше не возвращает `SQL_STILL_EXECUTING`.|
|[AFX_SQL_ASYNC](#afx_sql_async)|Вызывает `AFX_ODBC_CALL`.|
|[AFX_SQL_SYNC](#afx_sql_sync)|Вызывает функцию ODBC API, который не возвращает `SQL_STILL_EXECUTING`.|

### <a name="database-globals"></a>Глобальные значения базы данных

|||
|-|-|
|[AfxDbInitModule](#afxdbinitmodule)|Добавляет поддержку базы данных для обычной библиотеки DLL MFC, динамически компонуемые с MFC.|
|[AfxGetHENV](#afxgethenv)|Извлекает дескриптор среды ODBC в настоящий момент каким MFC. Вы можете использовать этот дескриптор в прямые вызовы ODBC.|


## <a name="afxdbinitmodule"></a> AfxDbInitModule

Для баз данных MFC (или DAO) поддерживает регулярных DLL MFC, динамически компонуемые с MFC, добавьте вызов данной функции в библиотеке регулярных DLL MFC `CWinApp::InitInstance` функцию для инициализации MFC базы данных библиотеки DLL.

### <a name="syntax"></a>Синтаксис

```
void AFXAPI AfxDbInitModule( );
```

### <a name="remarks"></a>Примечания

Убедитесь, что этот вызов происходит перед любой вызов базового класса или любого добавленного кода обращается к базе данных MFC DLL. Базы данных MFC DLL является расширением MFC DLL. в порядке для библиотеки DLL расширения MFC в `CDynLinkLibrary` цепочки, его необходимо создать `CDynLinkLibrary` объект в контексте каждого модуля, он будет использоваться. `AfxDbInitModule` Создает `CDynLinkLibrary` объекта в контексте библиотеки регулярных DLL MFC, таким образом, чтобы он получает встроены в `CDynLinkLibrary` объект цепочки обычной библиотеки DLL MFC.

### <a name="requirements"></a>Требования

**Заголовок:** \<afxdll_.h >

### <a name="see-also"></a>См. также

[Макросы и глобальные объекты](mfc-macros-and-globals.md)



##  <a name="afx_odbc_call"></a>  AFX_ODBC_CALL

Используйте этот макрос для вызова любой функции ODBC API, могут возвращать `SQL_STILL_EXECUTING`.

```
AFX_ODBC_CALL(SQLFunc)
```

### <a name="parameters"></a>Параметры

*SQLFunc*<br/>
Функции ODBC API. Дополнительные сведения о функции ODBC API см. в разделе Windows SDK.

### <a name="remarks"></a>Примечания

`AFX_ODBC_CALL` несколько раз вызывает функцию до его больше не возвращает `SQL_STILL_EXECUTING`.

Перед вызовом `AFX_ODBC_CALL`, необходимо объявить переменную, `nRetCode`, типа RETCODE.

Обратите внимание на то, что MFC ODBC классы сейчас используется только синхронная обработка. Чтобы выполнить асинхронную операцию, необходимо вызвать функцию ODBC API `SQLSetConnectOption`. Дополнительные сведения см. в разделе «Выполнение функции асинхронно» в пакете Windows SDK.


### <a name="example"></a>Пример

В этом примере используется `AFX_ODBC_CALL` для вызова `SQLColumns` функции ODBC API, которая возвращает список столбцов в таблице с именем, `strTableName`. Обратите внимание на объявление `nRetCode` и использование элементов данных набора записей для передачи параметров в функцию. В примере также демонстрируется проверка результатов вызова с `Check`, функция-член класса `CRecordset`. Переменная `prs` — это указатель на `CRecordset` объект, объявленные в другом месте.

[!code-cpp[NVC_MFCDatabase#39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

##  <a name="afx_sql_async"></a>  AFX_SQL_ASYNC

Реализация этого макроса, изменения в MFC 4.2.

```
AFX_SQL_ASYNC(prs, SQLFunc)
```

### <a name="parameters"></a>Параметры

*запросы на Вытягивание*<br/>
Указатель на `CRecordset` объекта или `CDatabase` объекта. Начиная с версии 4.2 MFC, значение этого параметра игнорируется.

*SQLFunc*<br/>
Функции ODBC API. Дополнительные сведения о функции ODBC API см. в разделе Windows SDK.

### <a name="remarks"></a>Примечания

`AFX_SQL_ASYNC` просто вызывает макрос [AFX_ODBC_CALL](#afx_odbc_call) и игнорирует *запросы на Вытягивание* параметра. В версиях MFC до 4.2 `AFX_SQL_ASYNC` использовался для вызова функций ODBC API, которые могут возвращать `SQL_STILL_EXECUTING`. Если функции ODBC API возвратил `SQL_STILL_EXECUTING`, затем `AFX_SQL_ASYNC` вызовет `prs->OnWaitForDataSource`.

> [!NOTE]
>  Классы MFC ODBC теперь использовать только синхронную обработку. Чтобы выполнить асинхронную операцию, необходимо вызвать функцию ODBC API `SQLSetConnectOption`. Дополнительные сведения см. в разделе «Выполнение функции асинхронно» в пакете Windows SDK.

### <a name="requirements"></a>Требования

  **Заголовок** afxdb.h

##  <a name="afx_sql_sync"></a>  AFX_SQL_SYNC

`AFX_SQL_SYNC` Макрос просто вызывает функцию `SQLFunc`.

```
AFX_SQL_SYNC(SQLFunc)
```

### <a name="parameters"></a>Параметры

*SQLFunc*<br/>
Функции ODBC API. Дополнительные сведения об этих функциях см. в разделе Windows SDK.

### <a name="remarks"></a>Примечания

Используйте этот макрос для вызова функций ODBC API, которые не будут возвращать `SQL_STILL_EXECUTING`.

Перед вызовом `AFX_SQL_SYNC`, необходимо объявить переменную, `nRetCode`, типа RETCODE. Можно проверить значение `nRetCode` после вызова макроса.

Обратите внимание, что реализация `AFX_SQL_SYNC` изменения в MFC 4.2. Так как проверка состояния сервера больше не требуется, `AFX_SQL_SYNC` просто присваивает значение свойству `nRetCode`. Например, вместо вызова

[!code-cpp[NVC_MFCDatabase#40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]

Вы можете просто задать назначения

[!code-cpp[NVC_MFCDatabase#41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxdb.h

##  <a name="afxgethenv"></a>  AfxGetHENV

Возвращенный дескриптор можно использовать в прямые вызовы ODBC, но не должно закрыть дескриптор или Предположим, что дескриптор является по-прежнему действующими и доступными после любых существующих `CDatabase`- или `CRecordset`-производных объектов будут уничтожены.

```
HENV AFXAPI AfxGetHENV();
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор среды ODBC в настоящий момент каким MFC. Может быть `SQL_HENV_NULL` при наличии не [CDatabase](../../mfc/reference/cdatabase-class.md) объекты и нет [CRecordset](../../mfc/reference/crecordset-class.md) используемых объектов.

### <a name="requirements"></a>Требования

  **Заголовок** afxdb.h

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
