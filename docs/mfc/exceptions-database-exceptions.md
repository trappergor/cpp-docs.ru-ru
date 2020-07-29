---
title: Исключения. Исключения баз данных
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
ms.openlocfilehash: aaed2a9f88c46a405b754b78242478f93cffda31
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217965"
---
# <a name="exceptions-database-exceptions"></a>Исключения. Исключения баз данных

В этой статье объясняется, как управлять исключениями базы данных. Большая часть материала этой статьи относится к работе с классами MFC для ODBC или классов MFC для объектов доступа к данным (DAO). Материал, относящийся к одной или другой модели, явно помечен. Будут рассмотрены следующие задачи:

- [Подходы к обработке исключений](#_core_approaches_to_exception_handling)

- [Пример обработки исключений базы данных](#_core_a_database_exception.2d.handling_example)

## <a name="approaches-to-exception-handling"></a><a name="_core_approaches_to_exception_handling"></a>Подходы к обработке исключений

Этот подход аналогичен при работе с DAO (устарел) или ODBC.

Всегда следует писать обработчики исключений для обработки исключительных условий.

Самым практичным подходом к перехвату исключений базы данных является тестирование приложения с помощью сценариев исключений. Определите вероятные исключения, которые могут возникнуть при выполнении операции в коде, и принудительно появление исключения. Затем изучите выходные данные трассировки, чтобы узнать, какое исключение возникает, или изучите возвращенные сведения об ошибке в отладчике. Это позволяет узнать, какие коды возврата будут отображаться для сценариев исключений, которые вы используете.

### <a name="error-codes-used-for-odbc-exceptions"></a>Коды ошибок, используемые для исключений ODBC

Помимо кодов возврата, определенных платформой, которые имеют имена форм **AFX_SQL_ERROR_XXX**, некоторые [кдбексцептионс](reference/cdbexception-class.md) основаны на кодах возврата [ODBC](../data/odbc/odbc-basics.md) . Коды возврата для таких исключений имеют имена в форме **SQL_ERROR_XXX**.

Коды возврата — как определяемые платформой, так и определяемые с помощью ODBC, которые могут возвращать классы базы данных, задокументированы в элементе данных [m_nRetCode](reference/cdbexception-class.md#m_nretcode) класса `CDBException`. Дополнительные сведения о кодах возврата, определенных ODBC, доступны в [справочнике программиста по ODBC](/sql/odbc/reference/odbc-programmer-s-reference).

### <a name="error-codes-used-for-dao-exceptions"></a>Коды ошибок, используемые для исключений DAO

Для исключений DAO обычно доступны дополнительные сведения. Доступ к сведениям об ошибках можно получить с помощью трех элементов данных перехваченного объекта [кдаоексцептион](reference/cdaoexception-class.md) :

- [m_pErrorInfo](reference/cdaoexception-class.md#m_perrorinfo) содержит указатель на объект [CDaoErrorInfo](reference/cdaoerrorinfo-structure.md) , который инкапсулирует сведения об ошибке в коллекцию объектов ошибок DAO, связанных с базой данных.

- [m_nAfxDaoError](reference/cdaoexception-class.md#m_nafxdaoerror) содержит расширенный код ошибки из классов MFC DAO. Эти коды ошибок, имена которых имеют форму **AFX_DAO_ERROR_XXX**, задокументированы в элементе данных в `CDaoException` .

- [m_scode](reference/cdaoexception-class.md#m_scode) содержит OLE **SCODE** из DAO, если это применимо. Однако вам редко приходится работать с этим кодом ошибки. Обычно дополнительные сведения доступны в двух других элементах данных. Дополнительные сведения о значениях **SCODE** см. в элементе Data.

Дополнительные сведения об ошибках DAO, типе объекта ошибки DAO и коллекции ошибок DAO доступны в разделе Class [кдаоексцептион](reference/cdaoexception-class.md).

## <a name="a-database-exception-handling-example"></a><a name="_core_a_database_exception.2d.handling_example"></a>Пример обработки исключений базы данных

В следующем примере предпринимается попытка создать объект, производный от [CRecordset](reference/crecordset-class.md), в куче с помощью **`new`** оператора, а затем открыть набор записей (для источника данных ODBC). Аналогичный пример для классов DAO см. в разделе "пример исключения DAO" ниже.

### <a name="odbc-exception-example"></a>Пример исключения ODBC

Функция [Open](reference/crecordset-class.md#open) Member может вызвать исключение (типа [КДБЕКСЦЕПТИОН](reference/cdbexception-class.md) для классов ODBC), поэтому этот код будет заключен в скобки `Open` с **`try`** блоком. Последующий **`catch`** блок будет перехватывать `CDBException` . Можно изучить сам объект Exception, вызываемый `e` , но в данном случае достаточно выяснить, что попытка создать набор записей не удалась. **`catch`** Блок отображает окно сообщения и очищается путем удаления объекта набора записей.

[!code-cpp[NVC_MFCDatabase#36](codesnippet/cpp/exceptions-database-exceptions_1.cpp)]

### <a name="dao-exception-example"></a>Пример исключения DAO

Пример DAO похож на пример для ODBC, но обычно можно получить дополнительные сведения. Следующий код также пытается открыть набор записей. Если эта предпринятая ошибка вызывает исключение, можно проверить элемент данных объекта исключения на наличие сведений об ошибке. Как и в предыдущем примере ODBC, может быть достаточно выяснить, что попытка создать набор записей завершилась ошибкой.

[!code-cpp[NVC_MFCDatabase#37](codesnippet/cpp/exceptions-database-exceptions_2.cpp)]

Этот код возвращает строку сообщения об ошибке из элемента [m_pErrorInfo](reference/cdaoexception-class.md#m_perrorinfo) объекта исключения. MFC заполняет этот элемент при возникновении исключения.

Описание сведений об ошибках, возвращаемых `CDaoException` объектом, см. в разделе classes [Кдаоексцептион](reference/cdaoexception-class.md) and [CDaoErrorInfo](reference/cdaoerrorinfo-structure.md).

При работе с базами данных Microsoft Jet (. mdb) и в большинстве случаев при работе с ODBC будет только один объект Error. В редких случаях при использовании источника данных ODBC и наличии нескольких ошибок можно выполнить цикл по коллекции ошибок DAO на основе числа ошибок, возвращенных [кдаоексцептион:: жетерроркаунт](reference/cdaoexception-class.md#geterrorcount). Каждый раз через цикл вызовите [кдаоексцептион:: жетерроринфо](reference/cdaoexception-class.md#geterrorinfo) , чтобы перезаполнить `m_pErrorInfo` элемент данных.

## <a name="see-also"></a>См. также раздел

[Обработка исключений](exception-handling-in-mfc.md)
