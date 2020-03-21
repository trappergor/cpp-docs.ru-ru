---
title: CCustomWindowsFile
ms.date: 10/22/2018
f1_keywords:
- cmyproviderwindowsfile
- ccustomwindowsfile
helpviewer_keywords:
- CMyProviderWindowsFile class
- OLE DB providers, wizard-generated files
- CCustomWindowsFile class
ms.assetid: 0e9e72ac-1e1e-445f-a7ac-690c20031f9d
ms.openlocfilehash: 103a1ce5568c6137994056e574ce8eec04511d8f
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079745"
---
# <a name="ccustomwindowsfile"></a>CCustomWindowsFile

Мастер создает класс с одной строкой данных. в этом случае он называется `CCustomWindowsFile`. Следующий код для `CCustomWindowsFile` создается мастером и перечисляет все файлы в каталоге с помощью структуры `WIN32_FIND_DATA`. `CCustomWindowsFile` наследуется от структуры `WIN32_FIND_DATA`:

```cpp
/////////////////////////////////////////////////////////////////////
// CustomRS.H

class CCustomWindowsFile:
   public WIN32_FIND_DATA
{
public:
BEGIN_PROVIDER_COLUMN_MAP(CCustomWindowsFile)
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)
END_PROVIDER_COLUMN_MAP()
};
```

`CCustomWindowsFile` называется [классом записей пользователя](../../data/oledb/user-record.md) , так как он также содержит карту, описывающую столбцы в наборе строк поставщика. Таблица столбцов поставщика содержит одну запись для каждого поля в наборе строк с помощью макросов PROVIDER_COLUMN_ENTRY. Макросы указывают имя столбца, порядковый номер и смещение для записи структуры. Записи столбцов поставщика в приведенном выше коде содержат смещения в структуре `WIN32_FIND_DATA`. Когда потребитель вызывает `IRowset::GetData`, данные передаются в один непрерывный буфер. Вместо того чтобы выполнять вычисления с помощью указателей, на карте можно указать элемент данных.

Класс `CCustomRowset` также содержит метод `Execute`. `Execute`, что фактически считывает данные из собственного источника. В следующем коде показан метод `Execute`, созданный мастером. Функция использует интерфейсы API `FindFirstFile` и `FindNextFile` Win32 для получения сведений о файлах в каталоге и помещает их в экземпляры класса `CCustomWindowsFile`.

```cpp
/////////////////////////////////////////////////////////////////////
// CustomRS.H

HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)
{
   USES_CONVERSION;
   BOOL bFound = FALSE;
   HANDLE hFile;
   LPTSTR  szDir = (m_strCommandText == _T("")) ? _T("*.*") :
       OLE2T(m_strCommandText);
   CCustomWindowsFile wf;
   hFile = FindFirstFile(szDir, &wf);
   if (hFile == INVALID_HANDLE_VALUE)
      return DB_E_ERRORSINCOMMAND;
   LONG cFiles = 1;
   BOOL bMoreFiles = TRUE;
   while (bMoreFiles)
   {
      if (!m_rgRowData.Add(wf))
         return E_OUTOFMEMORY;
      bMoreFiles = FindNextFile(hFile, &wf);
      cFiles++;
   }
   FindClose(hFile);
   if (pcRowsAffected != NULL)
      *pcRowsAffected = cFiles;
   return S_OK;
}
```

Каталог для поиска отображается `m_strCommandText`; Он содержит текст, представленный интерфейсом `ICommandText` в объекте Command. Если каталог не указан, используется текущий каталог.

Метод создает одну запись для каждого файла (соответствующего строке) и помещает ее в элемент данных `m_rgRowData`. Класс `CRowsetImpl` определяет элемент данных `m_rgRowData`. Данные в этом массиве показаны для всей таблицы и используются во всех шаблонах.

## <a name="see-also"></a>См. также:

[Созданные мастером поставщика файлы](../../data/oledb/provider-wizard-generated-files.md)<br/>
