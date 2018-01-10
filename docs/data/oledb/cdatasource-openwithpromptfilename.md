---
title: "CDataSource::OpenWithPromptFileName | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataSource.OpenWithPromptFileName
- OpenWithPromptFileName
- ATL::CDataSource::OpenWithPromptFileName
- ATL.CDataSource.OpenWithPromptFileName
- CDataSource::OpenWithPromptFileName
dev_langs: C++
helpviewer_keywords: OpenWithPromptFileName method
ms.assetid: 89460504-1aaf-4412-aa7b-fa5a4b39ada3
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 272fd65eb0fda3a087853ca3a5793618d356fc7e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdatasourceopenwithpromptfilename"></a>CDataSource::OpenWithPromptFileName
Этот метод отображает диалоговое окно, а затем открывает источник данных, используя указанный пользователем файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT OpenWithPromptFileName(   
   HWND hWnd = GetActiveWindow(   
   ),   
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_NONE,   
   LPCOLESTR szInitialDirectory = NULL    
) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `hWnd`  
 [входные данные] Дескриптор окна, которое является родительским объектом диалогового окна.  
  
 `dwPromptOptions`  
 [входные данные] Определяет стиль отображаемого диалогового окна выбора. Возможные значения см. в файле Msdasc.h.  
  
 *szInitialDirectory*  
 [входные данные] Исходный каталог для отображения в диалоговом окне выбора.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Этот метод открывает объект источника данных с помощью компонентов службы в oledb32.dll. Эта DLL-библиотека содержит реализацию возможностей компонентов службы, таких как создание пулов ресурсов, автоматическое прикрепление транзакций и т. д. Дополнительные сведения см. в разделе «Службы OLE DB» справочника программиста OLE DB на [http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDataSource](../../data/oledb/cdatasource-class.md)