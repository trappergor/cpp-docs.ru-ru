---
title: "CDataSource::Open | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDataSource::Open
- ATL.CDataSource.Open
- CDataSource::Open
- CDataSource.Open
dev_langs: C++
helpviewer_keywords: Open method
ms.assetid: a6d28bd1-799a-48ed-8993-5f82d1705b77
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3f2215b84600e2691f6b3aeb0407c5c6b96ebd00
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdatasourceopen"></a>CDataSource::Open
Открывает подключение к источнику данных с помощью **CLSID**, **ProgID**, или `CEnumerator` моникер или отображает диалоговое окно обнаружения.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 `clsid`  
 [in] **CLSID** поставщика данных.  
  
 *pPropSet*  
 [in] Указатель на массив [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) структур, содержащих свойства и значения, задаваемые. В разделе [наборов свойств и группы свойств](https://msdn.microsoft.com/en-us/library/ms713696.aspx) в *справочника программиста OLE DB* в Windows SDK.  
  
 *nPropertySets*  
 [in] Число [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) структуры, передаются в *pPropSet* аргумент.  
  
 *pName*  
 [входные данные] Имя базы данных, к которой необходимо подключиться.  
  
 *pUserName*  
 [входные данные] Имя пользователя.  
  
 *pPassword*  
 [входные данные] Пароль пользователя.  
  
 `nInitMode`  
 [входные данные] Режим инициализации базы данных. В разделе [свойства инициализации](https://msdn.microsoft.com/en-us/library/ms723127.aspx)в *Справочник программиста OLE DB* в Windows SDK список допустимых режимов инициализации. Если значение `nInitMode` равно нулю, в набор свойств, используемых для открытия соединения, не включен режим инициализации.  
  
 `szProgID`  
 [входные данные] Идентификатор программы.  
  
 `enumerator`  
 [in] Объект [CEnumerator](../../data/oledb/cenumerator-class.md) объект, используемый для получения моникера для открытия соединения, если вызывающий объект не указывает **CLSID**.  
  
 `hWnd`  
 [входные данные] Дескриптор окна, которое является родительским объектом диалогового окна. При использовании перегрузки функции с параметром `hWnd` автоматически вызываются компоненты службы. Дополнительные сведения см. в примечаниях.  
  
 `dwPromptOptions`  
 [входные данные] Определяет стиль отображаемого диалогового окна выбора. Возможные значения см. в файле Msdasc.h.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Эта перегрузка метода, использующая параметр `hWnd`, открывает объект источника данных с помощью компонентов службы в oledb32.dll. Эта DLL-библиотека содержит реализацию функций компонентов службы, таких как создание пулов ресурсов, автоматическое прикрепление транзакций и т. д. Дополнительные сведения см. в разделе «Службы OLE DB» справочника программиста OLE DB на [http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
 Перегрузки метода, которые не используют параметр `hWnd`, открывают объект источника данных без использования компонентов службы oledb32.dll. Объект [CDataSource](../../data/oledb/cdatasource-class.md) открытый с помощью этих перегрузок функций не сможет использовать возможности компонентов службы.  
  
## <a name="example"></a>Пример  
 В следующем коде показано, как открыть источник данных Jet 4.0 с помощью шаблонов OLE DB. Источник данных Jet обрабатывается так же, как источник данных OLE DB. Тем не менее при вызове **откройте** требуется два набора свойства: один для **DBPROPSET_DBINIT** , а другой для **DBPROPSET_JETOLEDB_DBINIT**, после чего можно задать  **DBPROP_JETOLEDB_DATABASEPASSWORD**.  
  
 [!code-cpp[NVC_OLEDB_Consumer#7](../../data/oledb/codesnippet/cpp/cdatasource-open_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDataSource](../../data/oledb/cdatasource-class.md)