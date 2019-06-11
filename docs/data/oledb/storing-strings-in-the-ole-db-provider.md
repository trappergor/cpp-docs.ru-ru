---
title: Хранение строк в поставщике OLE DB
ms.date: 05/09/2019
helpviewer_keywords:
- user records, editing
ms.assetid: 36cb9635-067c-4cad-8f85-962f28026f6a
ms.openlocfilehash: f0ae4a3718858c4de5417aaf5a4f9bc0c0ba9984
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2019
ms.locfileid: "65525352"
---
# <a name="storing-strings-in-the-ole-db-provider"></a>Хранение строк в поставщике OLE DB

> [!NOTE] 
> Мастер поставщика OLE DB в ATL недоступен в Visual Studio 2019 и более поздних версиях.


В файле *Custom*RS.h **мастер поставщика OLE DB в ATL** создает запись пользователя по умолчанию с именем `CWindowsFile`. Для обработки этих двух строк измените `CWindowsFile` следующим образом:

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

Элементы данных `szCommand` и `szText` представляют две строки с `szCommand2` и `szText2` с дополнительными столбцами (при необходимости). Элемент данных `dwBookmark` не нужен для этого простого поставщика с доступом только для чтения, но будет использоваться позднее для добавления интерфейса `IRowsetLocate`; см. статью [Enhancing the Simple Read Only Provider](../../data/oledb/enhancing-the-simple-read-only-provider.md) (Улучшение простого поставщика с доступом только для чтения). Оператор `==` сравнивает экземпляры (реализация этого оператора необязательна).

По завершении вы можете добавить функциональность для [считывания строк в поставщик OLE DB](../../data/oledb/reading-strings-into-the-ole-db-provider.md).

## <a name="see-also"></a>См. также

[Реализация простого поставщика, предназначенного только для чтения](../../data/oledb/implementing-the-simple-read-only-provider.md)<br/>
