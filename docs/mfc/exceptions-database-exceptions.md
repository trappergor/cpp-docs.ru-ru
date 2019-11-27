---
title: Исключения. Исключения базы данных
ms.date: 09/17/2019
helpviewer_keywords:
- DAO [MFC], exceptions
- exceptions [MFC], database
- exception handling [MFC], databases
- ODBC exceptions [MFC]
- ODBC [MFC], exceptions
- database exceptions [MFC]
- databases [MFC], exception handling
- error codes [MFC], database exception handling
ms.assetid: 28daf260-f824-4be6-aecc-1f859e6dec26
ms.openlocfilehash: c279c5b788cc7bd8a68fe36128c116d8df91c2eb
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2019
ms.locfileid: "71095813"
---
# <a name="exceptions-database-exceptions"></a>Исключения. Исключения базы данных

В этой статье объясняется, как управлять исключениями базы данных. Большая часть материала этой статьи относится к работе с классами MFC для ODBC или классов MFC для объектов доступа к данным (DAO). Материал, относящийся к одной или другой модели, явно помечен. Ниже приведен список разделов.

- [Подходы к обработке исключений](#_core_approaches_to_exception_handling)

- [Пример обработки исключений базы данных](#_core_a_database_exception.2d.handling_example)

##  <a name="_core_approaches_to_exception_handling"></a>Подходы к обработке исключений

Этот подход аналогичен при работе с DAO (устарел) или ODBC.

Всегда следует писать обработчики исключений для обработки исключительных условий.

Самым практичным подходом к перехвату исключений базы данных является тестирование приложения с помощью сценариев исключений. Определите вероятные исключения, которые могут возникнуть при выполнении операции в коде, и принудительно появление исключения. Затем изучите выходные данные трассировки, чтобы узнать, какое исключение возникает, или изучите возвращенные сведения об ошибке в отладчике. Это позволяет узнать, какие коды возврата будут отображаться для сценариев исключений, которые вы используете.

### <a name="error-codes-used-for-odbc-exceptions"></a>Коды ошибок, используемые для исключений ODBC

Помимо кодов возврата, определенных платформой, имеющих имена формы **AFX_SQL_ERROR_XXX**, некоторые [кдбексцептионс](../mfc/reference/cdbexception-class.md) основаны на кодах возврата [ODBC](../data/odbc/odbc-basics.md) . Коды возврата для таких исключений имеют имена в формате **SQL_ERROR_XXX**.

Коды возврата — как определяемые платформой, так и определяемые с помощью ODBC, которые могут возвращать классы базы данных, задокументированы в элементе данных [m_nRetCode](../mfc/reference/cdbexception-class.md#m_nretcode) класса `CDBException`. Дополнительные сведения о кодах возврата, определенных ODBC, доступны в *справочнике программиста* по ODBC SDK в библиотеке MSDN.

### <a name="error-codes-used-for-dao-exceptions"></a>Коды ошибок, используемые для исключений DAO

Для исключений DAO обычно доступны дополнительные сведения. Доступ к сведениям об ошибках можно получить с помощью трех элементов данных перехваченного объекта [кдаоексцептион](../mfc/reference/cdaoexception-class.md) :

- [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) содержит указатель на объект [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md) , который инкапсулирует сведения об ошибке в коллекцию объектов ошибок DAO, связанных с базой данных.

- [m_nAfxDaoError](../mfc/reference/cdaoexception-class.md#m_nafxdaoerror) содержит расширенный код ошибки из классов MFC DAO. Эти коды ошибок, имена которых имеют форму **AFX_DAO_ERROR_XXX**, задокументированы в элементе данных в `CDaoException`.

- [m_scode](../mfc/reference/cdaoexception-class.md#m_scode) содержит объект OLE **SCODE** из DAO, если это применимо. Однако вам редко приходится работать с этим кодом ошибки. Обычно дополнительные сведения доступны в двух других элементах данных. Дополнительные сведения о значениях **SCODE** см. в элементе Data.

Дополнительные сведения об ошибках DAO, типе объекта ошибки DAO и коллекции ошибок DAO доступны в разделе Class [кдаоексцептион](../mfc/reference/cdaoexception-class.md).

##  <a name="_core_a_database_exception.2d.handling_example"></a>Пример обработки исключений базы данных

В следующем примере предпринимается попытка создать объект, производный от [CRecordset](../mfc/reference/crecordset-class.md), в куче с помощью оператора **New** , а затем открыть набор записей (для источника данных ODBC). Аналогичный пример для классов DAO см. в разделе "пример исключения DAO" ниже.

### <a name="odbc-exception-example"></a>Пример исключения ODBC

Функция [Open](../mfc/reference/crecordset-class.md#open) Member может вызвать исключение (типа [кдбексцептион](../mfc/reference/cdbexception-class.md) для классов ODBC), поэтому этот код будет заключен в `Open` скобки с блоком **try** . Последующий блок **catch** будет перехватывать `CDBException`. Можно изучить сам объект Exception, вызываемый `e`, но в данном случае достаточно выяснить, что попытка создать набор записей не удалась. Блок **catch** отображает окно сообщения и очищается путем удаления объекта набора записей.

[!code-cpp[NVC_MFCDatabase#36](../mfc/codesnippet/cpp/exceptions-database-exceptions_1.cpp)]

### <a name="dao-exception-example"></a>Пример исключения DAO

Пример DAO похож на пример для ODBC, но обычно можно получить дополнительные сведения. Следующий код также пытается открыть набор записей. Если эта предпринятая ошибка вызывает исключение, можно проверить элемент данных объекта исключения на наличие сведений об ошибке. Как и в предыдущем примере ODBC, может быть достаточно выяснить, что попытка создать набор записей завершилась ошибкой.

[!code-cpp[NVC_MFCDatabase#37](../mfc/codesnippet/cpp/exceptions-database-exceptions_2.cpp)]

Этот код возвращает строку сообщения об ошибке из элемента [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) объекта исключения. MFC заполняет этот элемент при возникновении исключения.

Описание сведений об ошибках, возвращаемых `CDaoException` объектом, см. в разделе classes [кдаоексцептион](../mfc/reference/cdaoexception-class.md) and [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md).

При работе с базами данных Microsoft Jet (. mdb) и в большинстве случаев при работе с ODBC будет только один объект Error. В редких случаях при использовании источника данных ODBC и наличии нескольких ошибок можно выполнить цикл по коллекции ошибок DAO на основе числа ошибок, возвращенных [кдаоексцептион:: жетерроркаунт](../mfc/reference/cdaoexception-class.md#geterrorcount). Каждый раз через цикл вызовите [кдаоексцептион:: жетерроринфо](../mfc/reference/cdaoexception-class.md#geterrorinfo) , чтобы перезаполнить `m_pErrorInfo` элемент данных.

## <a name="see-also"></a>См. также

[Обработка исключений](../mfc/exception-handling-in-mfc.md)
