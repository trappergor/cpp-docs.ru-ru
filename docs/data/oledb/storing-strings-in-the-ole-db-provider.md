---
title: Хранение строк в поставщике OLE DB
ms.date: 10/26/2018
helpviewer_keywords:
- user records, editing
ms.assetid: 36cb9635-067c-4cad-8f85-962f28026f6a
ms.openlocfilehash: 5dce7dac84ef69da17baac135a68bd78698c4456
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026413"
---
# <a name="storing-strings-in-the-ole-db-provider"></a>Хранение строк в поставщике OLE DB

В *Custom*RS.h, **мастер поставщика ATL OLE DB** создает запись пользователя по умолчанию с именем `CWindowsFile`. Для обработки двух строк, изменить `CWindowsFile` как показано в следующем коде:

```cpp
////////////////////////////////////////////////////////////////////////
class CCustomWindowsFile:
   public WIN32_FIND_DATA
{
public:
DWORD dwBookmark;
static const int iSize = 256;    // Add this
TCHAR szCommand[iSize];          // Add this
TCHAR szText[iSize];             // Add this
TCHAR szCommand2[iSize];         // Add this
TCHAR szText2[iSize];            // Add this

BEGIN_PROVIDER_COLUMN_MAP(CCustomWindowsFile)
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)

   PROVIDER_COLUMN_ENTRY_STR("Command", 6, szCommand)    // Add this
   PROVIDER_COLUMN_ENTRY_STR("Text", 7, szText)          // Add this
   PROVIDER_COLUMN_ENTRY_STR("Command2", 8, szCommand2)  // Add this
   PROVIDER_COLUMN_ENTRY_STR("Text2", 9, szText2)        // Add this
END_PROVIDER_COLUMN_MAP()

   bool operator==(const CCustomWindowsFile& am) // This is optional
   {
      return (lstrcmpi(cFileName, am.cFileName) == 0);
   }
};
```

Члены данных `szCommand` и `szText` представляют две строки с `szCommand2` и `szText2` с дополнительными столбцами, при необходимости. Элемент данных `dwBookmark` не нужен для этого простого поставщика только для чтения, но будет использоваться позднее для добавления `IRowsetLocate` интерфейс; см. в разделе [Усовершенствование простого чтения только поставщика](../../data/oledb/enhancing-the-simple-read-only-provider.md). `==` Оператор сравнивает экземпляры (реализация этот оператор является необязательным).

Если это сделано, можно добавить функциональные возможности [чтение строк в поставщике OLE DB](../../data/oledb/reading-strings-into-the-ole-db-provider.md).

## <a name="see-also"></a>См. также

[Реализация простого поставщика, предназначенного только для чтения](../../data/oledb/implementing-the-simple-read-only-provider.md)<br/>
