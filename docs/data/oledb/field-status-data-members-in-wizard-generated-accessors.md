---
title: Статус поля элементов данных в мастере создания методов доступа
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB consumer templates, field status
- field status in OLE DB templates
ms.assetid: 66e4e223-c60c-471e-860d-d23abcdfe371
ms.openlocfilehash: 476c91f55071f6d1c7f243257273a32798813cae
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924641"
---
# <a name="field-status-data-members-in-wizard-generated-accessors"></a>Статус поля элементов данных в мастере создания методов доступа

::: moniker range="msvc-160"

Мастер объекта-получателя ATL OLE DB недоступен в Visual Studio 2019 и более поздних версиях. Эту функцию все еще можно добавить вручную. Дополнительные сведения см. в статье [Создание объекта-получателя без помощи мастера](creating-a-consumer-without-using-a-wizard.md).

::: moniker-end

::: moniker range="<=msvc-150"

При использовании службы **Мастер потребителя ATL OLE DB** для создания объекта-получателя в классе записей пользователя для каждого поля, указанного в сопоставлении столбцов, служба создает элемент данных. Каждый элемент данных имеет тип `DWORD` и содержит значение состояния, соответствующее его полю.

Например, для элемента данных *m_OwnerID* мастер создает два дополнительных элемента данных: один — для поля состояния ( *dwOwnerIDStatus* ) и другой — для длины полей ( *dwOwnerIDLength* ). Он также создает схему столбца с элементами COLUMN_ENTRY_LENGTH_STATUS.

Это продемонстрировано в приведенном ниже коде.

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

Вы можете использовать значения состояния для отладки. Если код, созданный **Мастером потребителя ATL OLE DB** , выдает ошибки компиляции, например DB_S_ERRORSOCCURRED или DB_E_ERRORSOCCURRED, необходимо просмотреть текущие значения состояния элементов данных поля. Те, которые имеют ненулевые значения, соответствуют ошибочным столбцам.

Вы также можете использовать значения состояния, чтобы присвоить значение NULL определенному полю. Это даст возможность отличить значение поля NULL от нулевого значения. Является ли NULL допустимым или специальным значением и способ его обработки приложением зависит только от вас. OLE DB определяет DBSTATUS_S_ISNULL как правильное средство, указывая универсальное значение NULL. Если объект-получатель считывает данные и значение оказывается нулевым, в поле состояния устанавливается значение DBSTATUS_S_ISNULL. Если необходимо установить значение NULL, объект-получатель задает значение состояния DBSTATUS_S_ISNULL перед вызовом поставщика.

Далее откройте Oledb.h и выполните поиск DBSTATUSENUM. Теперь вы можете сопоставить числовое значение ненулевого состояния и значения перечисления DBSTATUSENUM. Если имя перечисления вам ни о чем не говорит, см. тему **Состояние** раздела **Привязка значений данных** статьи [Руководство программиста OLE DB](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming). Эта тема содержит таблицы значений состояния, используемых при получении или задании данных. Сведения о значениях длины см. в теме **Длина** того самого раздела.

## <a name="retrieving-the-length-or-status-of-a-column"></a>Получение длины или состояния столбца

Вы можете получить длину столбца переменной длины или состояние столбца (например, для проверки DBSTATUS_S_ISNULL).

- Чтобы получить длину, используйте макрос COLUMN_ENTRY_LENGTH.

- Чтобы получить состояние, используйте макрос COLUMN_ENTRY_STATUS.

- Чтобы получить оба значения, используйте COLUMN_ENTRY_LENGTH_STATUS, как показано в примере ниже.

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

- Затем получите доступ к длине или состоянию, как показано в примере ниже.

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

При использовании `CDynamicAccessor` длина и состояние привязываются автоматически. Чтобы получить значения длины и состояния, используйте функции-члены `GetLength` и `GetStatus`.

::: moniker-end

## <a name="see-also"></a>См. также статью

[Работа с шаблонами потребителей OLE DB](../../data/oledb/working-with-ole-db-consumer-templates.md)
