---
title: Статус поля элементов данных в мастере создания методов доступа
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB consumer templates, field status
- field status in OLE DB templates
ms.assetid: 66e4e223-c60c-471e-860d-d23abcdfe371
ms.openlocfilehash: dd650b7cafef78e23c23ddfef791c88b6b93727f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025076"
---
# <a name="field-status-data-members-in-wizard-generated-accessors"></a>Статус поля элементов данных в мастере создания методов доступа

При использовании **Мастер потребителя ATL OLE DB** для создания получателя, мастер создает данные-член в класс записей пользователя для каждого поля, указанного в сопоставлении столбцов. Каждый элемент данных имеет тип `DWORD` и содержит значение состояния, соответствующее соответствующему полю.

Например, для элемента данных *m_OwnerID*, мастер создает дополнительный член данных для поля состояния (*dwOwnerIDStatus*) и еще один — для длины полей (*dwOwnerIDLength*). Она также создает схему столбца со COLUMN_ENTRY_LENGTH_STATUS элементами.

Это показано в следующем коде:

```cpp
class CAuthorsAccessor
{
public:
   LONG m_AuID;
   TCHAR m_Author[53];
   LONG m_YearBorn;

   DBSTATUS m_dwAuIDStatus;
   DBSTATUS m_dwAuthorStatus;
   DBSTATUS m_dwYearBornStatus;

   DBLENGTH m_dwAuIDLength;
   DBLENGTH m_dwAuthorLength;
   DBLENGTH m_dwYearBornLength;

    DEFINE_COMMAND_EX(CAuthorsAccessor, L" \
    SELECT \
        AuID, \
        Author, \
        YearBorn \
        FROM dbo.Authors")

    BEGIN_COLUMN_MAP(CAuthorsAccessor)
       COLUMN_ENTRY_LENGTH_STATUS(1, m_AuID, dwAuIDLength, dwAuIDStatus)
       COLUMN_ENTRY_LENGTH_STATUS(2, m_Author, dwAuthorLength, dwAuthorStatus)
       COLUMN_ENTRY_LENGTH_STATUS(3, m_YearBorn, dwYearBornLength, dwYearBornStatus)
    END_COLUMN_MAP()
...
```

> [!NOTE]
> Если вы изменяете класс записей пользователя или создаете собственного потребителя, переменные данных должны находиться перед переменными состояния и длины.

Значения состояния можно использовать для отладки. Если созданный код **Мастер потребителя ATL OLE DB** производит ошибки компиляции, например DB_S_ERRORSOCCURRED или DB_E_ERRORSOCCURRED, необходимо просмотреть текущие значения членов данных состояния поля. Те, которые имеют ненулевые значения соответствуют столбцам, вызывающим ошибки.

Значения состояния также можно присвоить значение NULL для определенного поля. Это помогает в случаях, когда необходимо отличать друг значение поля как значение NULL, а не с нуля. Это можно решить, является ли NULL допустимым значением или специальное значение, а также решить, каким образом приложение необходимо обработать его. OLE DB определяет DBSTATUS_S_ISNULL как правильные средства, указав универсальный значение NULL. Если потребитель считывает данные и имеет значение null, в поле состояния устанавливается в значение DBSTATUS_S_ISNULL. Если необходимо установить значение NULL, потребитель задает значение состояния DBSTATUS_S_ISNULL перед вызовом поставщика.

Затем откройте Oledb.h и выполните поиск DBSTATUSENUM. Затем можно сопоставить численного значения перечисления DBSTATUSENUM ненулевое значение состояния. Если имя перечисления не является достаточно сказать, что не так, см. в разделе **состояние** подразделы **привязки значения данных** раздел [Руководство программиста OLE DB](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming). Этот раздел содержит таблицы значений состояния, используемый при получении или задании данных. Сведения о значениях длины см. в разделе **длина** раздела в одном разделе.

## <a name="retrieving-the-length-or-status-of-a-column"></a>Получение длины или состояния столбца

Можно получить длину столбца переменной длины или изменении состояния столбца (например проверки DBSTATUS_S_ISNULL):

- Чтобы получить длину, используйте column_entry_length-макрос.

- Чтобы получить состояние, используйте column_entry_status-макрос.

- Чтобы получить оба, используйте COLUMN_ENTRY_LENGTH_STATUS, как показано:

    ```cpp
    class CProducts
    {
    public:
       char      szName[40];
       long      nNameLength;
       DBSTATUS   nNameStatus;

    BEGIN_COLUMN_MAP(CProducts)
    // Bind the column to CProducts.m_ProductName.
    // nOrdinal is zero-based, so the column number of m_ProductName is 1.
       COLUMN_ENTRY_LENGTH_STATUS(1, szName, nNameLength, nNameStatus)
    END_COLUMN_MAP()
    };
    ```

- Затем получить доступ к длины или состоянии как показано:

    ```cpp
    CTable<CAccessor<CProducts >> product;
    CSession session;

    product.Open(session, "Product");

    while (product.MoveNext() == S_OK)
    {
       // Check the product name isn't NULL before tracing it
       if (product.nNameStatus == DBSTATUS_S_OK)
          ATLTRACE("%s is %d characters\n", product.szName, product.nNameLength);
    }
    ```

При использовании `CDynamicAccessor`, длина и состояние привязываются автоматически. Чтобы получить значения длины и состояния, используйте `GetLength` и `GetStatus` функций-членов.

## <a name="see-also"></a>См. также

[Работа с шаблонами объекта-получателя OLE DB](../../data/oledb/working-with-ole-db-consumer-templates.md)