---
title: "CDataSource::Open | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDataSource::Open"
  - "ATL.CDataSource.Open"
  - "CDataSource::Open"
  - "CDataSource.Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open - метод"
ms.assetid: a6d28bd1-799a-48ed-8993-5f82d1705b77
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataSource::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Открывает подключение к источнику данных, используя **CLSID**, **ProgID**, или моникер `CEnumerator`, или отображает диалоговое окно для выбора.  
  
## Синтаксис  
  
```  
  
        HRESULT Open(  
   const CLSID& clsid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(  
   const CLSID& clsid,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0   
) throw( );  
HRESULT Open(  
   LPCTSTR szProgID,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(  
   LPCTSTR szProgID,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0   
) throw( );  
HRESULT Open(  
   const CEnumerator& enumerator,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(  
   const CEnumerator& enumerator,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0   
) throw( );  
HRESULT Open(  
   HWND hWnd = GetActiveWindow( ),  
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_WIZARDSHEET   
) throw( );  
HRESULT Open(   
   LPCWSTR szProgID,   
   DBPROPSET* pPropSet = NULL,   
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(   
   LPCSTR szProgID,   
   LPCTSTR pName,   
   LPCTSTR pUserName = NULL,   
   LPCTSTR pPassword = NULL,   
   long nInitMode = 0   
) throw( );  
```  
  
#### Параметры  
 `clsid`  
 \[входные данные\] **CLSID** поставщика данных.  
  
 *pPropSet*  
 \[входные данные\] Указатель на массив структур [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx), содержащих свойства и значения, которые требуется установить.  См. раздел [Наборы и группы свойств](https://msdn.microsoft.com/en-us/library/ms713696.aspx) *справочника программиста OLE DB* в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *nPropertySets*  
 \[входные данные\] Число структур [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx), переданных в аргументе *pPropSet*.  
  
 *pName*  
 \[входные данные\] Имя базы данных, к которой необходимо подключиться.  
  
 *pUserName*  
 \[входные данные\] Имя пользователя.  
  
 *pPassword*  
 \[входные данные\] Пароль пользователя.  
  
 `nInitMode`  
 \[входные данные\] Режим инициализации базы данных.  Список допустимых режимов инициализации см. в разделе [Свойства инициализации](https://msdn.microsoft.com/en-us/library/ms723127.aspx) *справочника программиста OLE DB* в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  Если значение `nInitMode` равно нулю, в набор свойств, используемых для открытия соединения, не включен режим инициализации.  
  
 `szProgID`  
 \[входные данные\] Идентификатор программы.  
  
 `enumerator`  
 \[входные данные\] Объект [CEnumerator](../../data/oledb/cenumerator-class.md) объект, используемый для получения моникера для открытия соединения, если вызывающий объект не указывает **CLSID**.  
  
 `hWnd`  
 \[входные данные\] Дескриптор окна, которое является родительским объектом диалогового окна.  При использовании перегрузки функции с параметром `hWnd` автоматически вызываются компоненты службы. Дополнительные сведения см. в примечаниях.  
  
 `dwPromptOptions`  
 \[входные данные\] Определяет стиль отображаемого диалогового окна выбора.  Возможные значения см. в файле Msdasc.h.  
  
## Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## Заметки  
 Эта перегрузка метода, использующая параметр `hWnd`, открывает объект источника данных с помощью компонентов службы в oledb32.dll. Эта DLL\-библиотека содержит реализацию функций компонентов службы, таких как создание пулов ресурсов, автоматическое прикрепление транзакций и т. д.  Подробнее см. в разделе "Службы OLE DB" справочника программиста OLE DB на странице [http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/oledb\/htm\/oledbole\_db\_services.asp?frame\=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
 Перегрузки метода, которые не используют параметр `hWnd`, открывают объект источника данных без использования компонентов службы oledb32.dll.  Объект [CDataSource](../Topic/CDataSource%20Class.md), открытый с помощью этих перегрузок функций, не сможет использовать возможности компонентов службы.  
  
## Пример  
 В следующем коде показано, как открыть источник данных Jet 4.0 с помощью шаблонов OLE DB.  Источник данных Jet обрабатывается так же, как источник данных OLE DB.  Тем не менее при вызове метода **Open** требуется два набора свойства: один для **DBPROPSET\_DBINIT**, а другой для **DBPROPSET\_JETOLEDB\_DBINIT**. Поэтому можно указать **DBPROP\_JETOLEDB\_DATABASEPASSWORD**.  
  
 [!code-cpp[NVC_OLEDB_Consumer#7](../../data/oledb/codesnippet/CPP/cdatasource-open_1.cpp)]  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDataSource](../Topic/CDataSource%20Class.md)