---
title: "Запись пользователя | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "поставщики OLE DB, запись пользователя"
  - "записи, пользователь"
  - "наборы строк, запись пользователя"
  - "записи пользователя"
  - "записи пользователя, описание"
ms.assetid: 9c0d2864-2738-4f62-a750-1016d9c3523f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Запись пользователя
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Пользовательская запись предоставляет код и структуру данных, представляющую данные столбца для набора строк.  Пользовательская запись может быть создана во время компиляции или выполнения.  При создании поставщика с помощью мастера поставщика ATL OLE DB мастер создает пользовательскую запись, имеющую следующий вид \(предполагается, что указано имя поставщика \[краткое имя\] "MyProvider"\):  
  
```  
class CWindowsFile:  
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
  
 Шаблоны поставщика OLE DB обрабатывают все характеристики OLE DB, касающиеся взаимодействия с клиентом.  Для получения необходимых для отклика данных столбца поставщик вызывает функцию `GetColumnInfo`, которую необходимо поместить в пользовательскую запись.  Можно явно переопределить оператор `GetColumnInfo` в пользовательской записи, например объявив его в H\-файле, как показано ниже:  
  
```  
template <class T>  
static ATLCOLUMNINFO* GetColumnInfo(T* pThis, ULONG* pcCols)   
```  
  
 Это соответствует следующей записи:  
  
```  
static ATLCOLUMNINFO* GetColumnInfo(CommandClass* pThis, ULONG* pcCols)  
static ATLCOLUMNINFO* GetColumnInfo(RowsetClass* pThis, ULONG* pcCols)  
```  
  
 Необходимо также обеспечить реализацию `GetColumnInfo` в CPP\-файле пользовательской записи.  
  
 Макрос PROVIDER\_COLUMN\_MAP создает функцию `GetColumnInfo`:  
  
-   BEGIN\_PROVIDER\_COLUMN\_MAP определяет прототип функции и статический массив структур **ATLCOLUMNINFO**.  
  
-   PROVIDER\_COLUMN\_ENTRY определяет и инициализирует одну структуру **ATLCOLUMNINFO**.  
  
-   END\_PROVIDER\_COLUMN\_MAP закрывает массив и функцию.  Он также помещает число элементов массива в параметр `pcCols`.  
  
 Если пользовательская запись создается во время выполнения, **GetColumnInfo** использует параметр `pThis` для получения указателя на набор строк или экземпляр команды.  Команды и наборы строк должны поддерживать интерфейс `IColumnsInfo`, чтобы из указателя могли быть извлечены сведения о столбцах.  
  
 **CommandClass** и **RowsetClass** являются командой и набором строк, использующими пользовательскую запись.  
  
 Более подробные примеры переопределения `GetColumnInfo` в пользовательской записи представлены в разделе [Динамическое определение столбцов для возврата потребителю](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## См. также  
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)