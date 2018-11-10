---
title: Чтение строк в поставщике OLE DB
ms.date: 10/13/2018
helpviewer_keywords:
- OLE DB providers, reading strings into
ms.assetid: 517f322c-f37e-4eed-bf5e-dd9a412c2f98
ms.openlocfilehash: 50df9f13b814eb00b309460894d704238bc3e7dc
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2018
ms.locfileid: "51264780"
---
# <a name="reading-strings-into-the-ole-db-provider"></a>Чтение строк в поставщике OLE DB

`CCustomRowset::Execute` Функция открывает файл и считывает строки. Потребитель передает имя файла для поставщика путем вызова [ICommandText::SetCommandText](/previous-versions/windows/desktop/ms709757). Поставщик получает имя файла и сохраняет его в переменной-члена `m_strCommandText`. `Execute` считывает имя файла из `m_strCommandText`. Если имя файла является недопустимым или недоступен, файл `Execute` возвращает сообщение об ошибке. В противном случае он открывает файл и вызовы `fgets` для извлечения строк. Для каждого набора строк его чтение, `Execute` создает экземпляр пользовательской записи (изменения `CCustomWindowsFile` из [хранения строк в поставщике OLE DB](../../data/oledb/storing-strings-in-the-ole-db-provider.md)) и помещает их в массив.

Если не удается открыть файл, `Execute` должен возвращать DB_E_NOTABLE. Если вместо этого он возвращает E_FAIL, поставщик не будет работать с объектами-получателями и не будет передавать OLE DB [проверка на совместимость с](../../data/oledb/testing-your-provider.md).

## <a name="example"></a>Пример

```cpp
/////////////////////////////////////////////////////////////////////////
// CustomRS.h
class CCustomRowset : public CRowsetImpl< CCustomRowset, CCustomWindowsFile, CCustomCommand>
{
public:
    HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)
    {
        enum {
            sizeOfBuffer = 256,
            sizeOfFile = MAX_PATH
        };
        USES_CONVERSION;
        FILE* pFile = NULL;
        TCHAR szString[sizeOfBuffer];
        TCHAR szFile[sizeOfFile];
        size_t nLength;

        ObjectLock lock(this);

        // From a filename, passed in as a command text, scan the file
        // placing data in the data array.
        if (!m_strCommandText)
        {
            ATLTRACE("No filename specified");
            return E_FAIL;
        }

        // Open the file
        _tcscpy_s(szFile, sizeOfFile, m_strCommandText);
        if (szFile[0] == _T('\0') ||
            (fopen_s(&pFile, (char*)&szFile[0], "r") == 0))
        {
            ATLTRACE("Could not open file");
            return DB_E_NOTABLE;
        }

        // Scan and parse the file.
        // The file should contain two strings per record
        LONG cFiles = 0;
        while (fgets((char*)szString, sizeOfBuffer, pFile) != NULL)
        {
            nLength = strnlen((char*)szString, sizeOfBuffer);
            szString[nLength-1] = '\0';   // Strip off trailing CR/LF
            CCustomWindowsFile am;
            _tcscpy_s(am.szCommand, am.iSize, szString);
            _tcscpy_s(am.szCommand2, am.iSize, szString);

            if (fgets((char*)szString, sizeOfBuffer, pFile) != NULL)
            {
                nLength = strnlen((char*)szString, sizeOfBuffer);
                szString[nLength-1] = '\0'; // Strip off trailing CR/LF
                _tcscpy_s(am.szText, am.iSize, szString);
                _tcscpy_s(am.szText2, am.iSize, szString);
            }

            am.dwBookmark = ++cFiles;
            if (!m_rgRowData.Add(am))
            {
                ATLTRACE("Couldn't add data to array");
                fclose(pFile);
                return E_FAIL;
            }
        }

        if (pcRowsAffected != NULL)
            *pcRowsAffected = cFiles;
        return S_OK;
    }
};
```

Если это сделано, ваш поставщик должен быть готовым для компиляции и выполнения. Чтобы протестировать поставщика, требуется объект-получатель с соответствующими функциями. [Реализация простых объектов получателей](../../data/oledb/implementing-a-simple-consumer.md) показано создание объекта-получателя для тестирования. Запустите тестовый объект-получатель с поставщиком и убедитесь, что тестовый объект-получатель получает соответствующие строки от поставщика.

После успешного тестирования поставщика можно расширить его функциональные возможности, реализовав дополнительные интерфейсы. Пример показан в [Усовершенствование простого поставщика только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md).

## <a name="see-also"></a>См. также

[Реализация простого поставщика, предназначенного только для чтения](../../data/oledb/implementing-the-simple-read-only-provider.md)<br/>
