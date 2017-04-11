---
title: "Макросы и глобальные объекты баз данных | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFXDB/AFX_ODBC_CALL
- AFXDB/AFX_SQL_ASYNC
- AFXDB/AFX_SQL_SYNC
- AFXDB/AfxGetHENV
dev_langs:
- C++
helpviewer_keywords:
- global database functions [C++]
- database macros [C++]
- database globals [C++]
- global functions [C++], database functions
- macros [C++], MFC database
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
caps.latest.revision: 13
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
ms.sourcegitcommit: b943ef8dd652df061965fe81ecc9c08115636141
ms.openlocfilehash: ddf13f6458df387d6686a18ecd459938ef2ebafd
ms.lasthandoff: 04/04/2017

---
# <a name="database-macros-and-globals"></a>Макросы и глобальные объекты баз данных
Макросы и глобальные объекты, перечисленные ниже применяются для приложений баз данных на основе ODBC. Они не используются в приложениях на основе DAO.  
  
 Прежде чем MFC версии 4.2, макросы `AFX_SQL_ASYNC` и `AFX_SQL_SYNC` дали возможность выдавать времени для других процессов асинхронных операций. Начиная с MFC версии 4.2, реализация этих макросов, изменить, так как классы MFC ODBC используется только для синхронных операций. Макрос `AFX_ODBC_CALL` впервые появился в MFC версии 4.2.  
  
### <a name="database-macros"></a>Макросы базы данных  
  
|||  
|-|-|  
|[AFX_ODBC_CALL](#afx_odbc_call)|Вызывает функцию ODBC API, который возвращает `SQL_STILL_EXECUTING`. `AFX_ODBC_CALL`несколько раз вызывает функцию до его больше не возвращает `SQL_STILL_EXECUTING`.|  
|[AFX_SQL_ASYNC](#afx_sql_async)|Вызывает `AFX_ODBC_CALL`.|  
|[AFX_SQL_SYNC](#afx_sql_sync)|Вызывает функцию ODBC API, который не возвращает `SQL_STILL_EXECUTING`.|  
  
### <a name="database-globals"></a>Глобальные значения базы данных  
  
|||  
|-|-| 
|[AfxDbInitModule](#afxdbinitmodule)|Добавляет поддержку базы данных для обычной DLL, динамически компонуемые с MFC.| 
|[AfxGetHENV](#afxgethenv)|Получает дескриптор среды ODBC используется в настоящее время с MFC. Этот дескриптор можно использовать в прямые вызовы ODBC.|  


## <a name="afxdbinitmodule"></a>AfxDbInitModule
Для базы данных MFC (или DAO) поддерживает из обычной DLL, динамически компонуемые с MFC, добавьте вызов этой функции в обычной DLL **CWinApp::InitInstance** функцию для инициализации MFC базы данных библиотеки DLL.  
   
### <a name="syntax"></a>Синтаксис    
```
void AFXAPI AfxDbInitModule( );    
```  
   
### <a name="remarks"></a>Примечания  
 Убедитесь, что этот вызов происходит перед любой вызов базового класса или добавлении каких-либо код, который обращается к базе данных библиотеки DLL MFC. Базы данных MFC DLL — это расширение DLL. Чтобы библиотеки DLL расширения в **CDynLinkLibrary** цепочки, его необходимо создать **CDynLinkLibrary** объект в контексте каждого модуля, он будет использоваться. `AfxDbInitModule`Создает **CDynLinkLibrary** объект в контексте обычной DLL так, чтобы он получает встроены в **CDynLinkLibrary** объекта цепочки обычной библиотеки DLL.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:**<afxdll_.h></afxdll_.h>  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)
 
  

##  <a name="afx_odbc_call"></a>AFX_ODBC_CALL  
 Используйте этот макрос, чтобы вызвать любую функцию ODBC API, который может вернуть `SQL_STILL_EXECUTING`.  
  
```  
AFX_ODBC_CALL(SQLFunc)  
```  
  
### <a name="parameters"></a>Параметры  
 `SQLFunc`  
 Функции ODBC API. Дополнительные сведения о функциях API-интерфейса ODBC см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 `AFX_ODBC_CALL`несколько раз вызывает функцию, пока она больше не возвращает `SQL_STILL_EXECUTING`.  
  
 Перед вызовом `AFX_ODBC_CALL`, необходимо объявить переменную, `nRetCode`, типа **RETCODE**.  
  
 Обратите внимание, что MFC ODBC классы теперь используйте только синхронная обработка. Чтобы выполнить асинхронную операцию, необходимо вызвать функцию API-интерфейса ODBC **SQLSetConnectOption**. Дополнительные сведения см. в разделе «Выполнение функции асинхронно» в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  

  
### <a name="example"></a>Пример  
 В этом примере используется `AFX_ODBC_CALL` для вызова **SQLColumns** функции ODBC API, которая возвращает список столбцов в таблице с именем `strTableName`. Обратите внимание, объявление `nRetCode` и использование элементов данных набора записей для передачи параметров в функцию. В примере также демонстрируется проверка результатов вызова с **проверьте**, функция-член класса `CRecordset`. Переменная `prs` — это указатель на `CRecordset` объект, объявленные в другом месте.  
  
 [!code-cpp[NVC_MFCDatabase #39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  

##  <a name="afx_sql_async"></a>AFX_SQL_ASYNC  
 Реализация этого макроса, изменения в MFC версии 4.2.  
  
```   
AFX_SQL_ASYNC(prs, SQLFunc)   
```  
  
### <a name="parameters"></a>Параметры  
 `prs`  
 Указатель на `CRecordset` объекта или `CDatabase` объекта. Начиная с MFC версии 4.2, значение этого параметра учитывается.  
  
 `SQLFunc`  
 Функции ODBC API. Дополнительные сведения о функциях API-интерфейса ODBC см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 `AFX_SQL_ASYNC`просто вызывает макрос [AFX_ODBC_CALL](#afx_odbc_call) и игнорирует `prs` параметра. В версиях до 4.2, MFC `AFX_SQL_ASYNC` был использован для вызова функций ODBC API, которые могут возвращать `SQL_STILL_EXECUTING`. Если было получено функцию ODBC API `SQL_STILL_EXECUTING`, затем `AFX_SQL_ASYNC` вызовет `prs->OnWaitForDataSource`.  
  
> [!NOTE]
>  Классы MFC ODBC теперь использовать только синхронную обработку. Чтобы выполнить асинхронную операцию, необходимо вызвать функцию API-интерфейса ODBC **SQLSetConnectOption**. Дополнительные сведения см. в разделе «Выполнение функции асинхронно» в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdb.h  
  
##  <a name="afx_sql_sync"></a>AFX_SQL_SYNC  
 `AFX_SQL_SYNC` Макрос просто вызывает функцию `SQLFunc`.  
  
```   
AFX_SQL_SYNC(SQLFunc)   
```  
  
### <a name="parameters"></a>Параметры  
 `SQLFunc`  
 Функции ODBC API. Дополнительные сведения об этих функциях см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для вызова функций ODBC API, которые не будут возвращать `SQL_STILL_EXECUTING`.  
  
 Перед вызовом метода `AFX_SQL_SYNC`, необходимо объявить переменную, `nRetCode`, типа **RETCODE**. Можно проверить значение `nRetCode` после вызова макроса.  
  
 Обратите внимание, что реализация `AFX_SQL_SYNC` изменения в MFC версии 4.2. Так как проверка состояния сервера больше не требуется, `AFX_SQL_SYNC` просто присваивает значение свойству `nRetCode`. Например, вместо вызова  
  
 [!code-cpp[NVC_MFCDatabase #40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]  
  
 можно просто сделать назначения  
  
 [!code-cpp[NVC_MFCDatabase #41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdb.h  
  
##  <a name="afxgethenv"></a>AfxGetHENV  
 Возвращенный дескриптор можно использовать в прямые вызовы ODBC, но не должно закрыть дескриптор или Предположим, что дескриптор все еще допустимой и доступной после любой существующий `CDatabase`- или `CRecordset`-производных объектов были уничтожены.  
  
```   
HENV AFXAPI AfxGetHENV(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор среды ODBC используется в настоящее время с MFC. Может быть `SQL_HENV_NULL` при наличии не [CDatabase](../../mfc/reference/cdatabase-class.md) объектов и нет [CRecordset](../../mfc/reference/crecordset-class.md) используемых объектов.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdb.h  
    
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

