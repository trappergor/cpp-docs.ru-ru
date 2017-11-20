---
title: "Считывание строк в поставщике OLE DB | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: OLE DB providers, reading strings into
ms.assetid: 517f322c-f37e-4eed-bf5e-dd9a412c2f98
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4c4c88f29cd0ad7989c079a17f66f1f48e4874a6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="reading-strings-into-the-ole-db-provider"></a>Чтение строк в поставщике OLE DB
`RMyProviderRowset::Execute` Функция открывает файл и читает строки. Потребитель передает имя файла для поставщика путем вызова [ICommandText::SetCommandText](https://msdn.microsoft.com/en-us/library/ms709757.aspx). Поставщик получает имя файла и сохраняет его в переменной-члена `m_szCommandText`. `Execute`считывает имя файла из `m_szCommandText`. Если имя файла является недопустимым, или файл недоступен, `Execute` возвращает сообщение об ошибке. В противном случае он открывает файл и вызывает метод `fgets` для извлечения строк. Для каждого набора строк, его чтение, `Execute` создает экземпляр пользовательской записи (`CAgentMan`) и помещает их в массив.  
  
 Если не удается открыть файл, `Execute` должен возвращать **DB_E_NOTABLE**. Если он возвращает **E_FAIL** вместо этого поставщик не будет работать с объектами-получателями и передавать OLE DB [проверка на совместимость с](../../data/oledb/testing-your-provider.md).  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 Отредактированная `Execute` функция выглядит следующим образом:  
  
### <a name="code"></a>Код  
  
```  
/////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
class RMyProviderRowset : public CRowsetImpl< RMyProviderRowset, CAgentMan, CRMyProviderCommand>  
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
        size_t nLength;        errcodeerr;  
  
        ObjectLock lock(this);  
  
        // From a filename, passed in as a command text, scan the file  
        // placing data in the data array.  
        if (!m_szCommandText)  
        {  
            ATLTRACE("No filename specified");  
            return E_FAIL;  
        }  
  
        // Open the file  
        _tcscpy_s(szFile, sizeOfFile, m_szCommandText);  
        if (szFile[0] == _T('\0') ||   
            ((err = fopen_s(&pFile, &szFile[0], "r")) == 0))  
        {  
            ATLTRACE("Could not open file");  
            return DB_E_NOTABLE;  
        }  
  
        // Scan and parse the file.  
        // The file should contain two strings per record  
        LONG cFiles = 0;  
        while (fgets(szString, sizeOfBuffer, pFile) != NULL)  
        {  
            nLength = strnlen(szString, sizeOfBuffer);  
            szString[nLength-1] = '\0';   // Strip off trailing CR/LF  
            CAgentMan am;  
            _tcscpy_s(am.szCommand, am.sizeOfCommand, szString);  
            _tcscpy_s(am.szCommand2, am.sizeOfCommand2, szString);  
  
            if (fgets(szString, sizeOfBuffer, pFile) != NULL)  
            {  
                nLength = strnlen(szString, sizeOfBuffer);  
                szString[nLength-1] = '\0'; // Strip off trailing CR/LF  
                _tcscpy_s(am.szText, am.sizeOfText, szString);  
                _tcscpy_s(am.szText2, am.sizeOfText2, szString);  
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
}  
```  
  
## <a name="see-also"></a>См. также  
 [Реализация простого поставщика, предназначенного только для чтения](../../data/oledb/implementing-the-simple-read-only-provider.md)