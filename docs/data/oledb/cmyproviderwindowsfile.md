---
title: "Класс CMyProviderWindowsFile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cmyproviderwindowsfile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMyProviderWindowsFile - класс"
  - "поставщики OLE DB, файлы, созданные мастером"
ms.assetid: 0e9e72ac-1e1e-445f-a7ac-690c20031f9d
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Класс CMyProviderWindowsFile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

С помощью мастера создается класс `CMyProviderWindowsFile`, который содержит одну строку данных.  Приведенный ниже код класса `CMyProviderWindowsFile` автоматически создается с помощью мастера и используется для перечисления всех файлов в каталоге с использованием структуры **WIN32\_FIND\_DATA**.  Класс `CMyProviderWindowsFile` наследуется от структуры **WIN32\_FIND\_DATA**:  
  
```  
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
class CMyProviderWindowsFile:   
   public WIN32_FIND_DATA  
{  
public:  
BEGIN_PROVIDER_COLUMN_MAP(CMyProviderWindowsFile)  
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)  
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)  
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)  
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)  
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)  
END_PROVIDER_COLUMN_MAP()  
};  
```  
  
 Класс `CMyProviderWindowsFile` также называется [классом записей пользователя](../../data/oledb/user-record.md), поскольку в нем содержится сопоставление, описывающее столбцы в наборе строк поставщика.  С помощью макроса PROVIDER\_COLUMN\_ENTRY в сопоставление столбцов поставщика включается одна запись для каждого поля в наборе строк.  В макросе устанавливается имя и порядковый номер столбца, а также значение его смещения относительно записи структуры.  В записях столбцов поставщика в приведенном выше коде содержится значение смещения в структуре **WIN32\_FIND\_DATA**.  При вызове объектом\-получателем метода **IRowset::GetData** данные передаются в один непрерывный буфер.  С помощью сопоставления можно указать член данных вместо выполнения арифметических операций с указателями.  
  
 Класс `CMyProviderRowset` также содержит метод `Execute`.  Метод `Execute` предназначен для считывания данных из источника.  В следующем примере показан созданный с помощью мастера метод `Execute`.  В этой функции API\-интерфейсы Win32 **FindFirstFile** и `FindNextFile` используются для извлечения и передачи в экземпляр класса `CMyProviderWindowsFile` сведений о расположенных в каталоге файлах.  
  
```  
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)  
{  
   USES_CONVERSION;  
   BOOL bFound = FALSE;  
   HANDLE hFile;  
   LPTSTR  szDir = (m_strCommandText == _T("")) ? _T("*.*") :  
       OLE2T(m_strCommandText);  
   CMyProviderWindowsFile wf;  
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
  
 Каталог для поиска определяется в переменной `m_strCommandText`, в которой содержится текст, предоставляемый интерфейсом `ICommandText` в объекте команды.  Если каталог не указан, поиск выполняется в текущем каталоге.  
  
 В этом методе для каждого файла создается одна запись \(соответствует строке\), которая помещается в член данных **m\_rgRowData**.  Член данных **m\_rgRowData** определяется в классе `CRowsetImpl`.  Данные в этом массиве представляют всю таблицу и используются во всех шаблонах.  
  
## См. также  
 [Созданные мастером поставщика файлы](../../data/oledb/provider-wizard-generated-files.md)