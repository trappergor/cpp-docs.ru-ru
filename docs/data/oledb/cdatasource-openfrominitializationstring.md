---
title: "CDataSource::OpenFromInitializationString | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataSource.OpenFromInitializationString
- OpenFromInitializationString
- CDataSource::OpenFromInitializationString
- ATL::CDataSource::OpenFromInitializationString
- ATL.CDataSource.OpenFromInitializationString
dev_langs:
- C++
helpviewer_keywords:
- OpenFromInitializationString method
ms.assetid: 5ef1f1fd-92a9-4e1c-ad80-d3601b094b8c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f05654c9b8647f62d967f97fa4b373471e049cda
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="cdatasourceopenfrominitializationstring"></a>CDataSource::OpenFromInitializationString
Открывает источник данных, указанной в строке инициализации, предоставленное пользователем.  
  
## <a name="syntax"></a>Синтаксис  
  
```
HRESULT OpenFromInitializationString(LPCOLESTR szInitializationString,   
   bool fPromptForInfo= false) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *szInitializationString*  
 [in] Строка инициализации.  
  
 *fPromptForInfo*  
 [in] Если этот аргумент имеет значение **true**, затем `OpenFromInitializationString` установит **DBPROP_INIT_PROMPT** свойства **DBPROMPT_COMPLETEREQUIRED**, который указывает, что пользователь ввести только в том случае, если необходима дополнительная информация. Это полезно в ситуациях, в которых в строке инициализации указан базы данных, которая требует наличия пароля, но строка не содержит пароль. Пользователю предлагается ввести пароль (или все отсутствующие сведения) при попытке подключения к базе данных.  
  
 Значение по умолчанию — **false**, которое указывает, что никогда не запрашивать пользователя (задает **DBPROP_INIT_PROMPT** для **DBPROMPT_NOPROMPT**).  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Этот метод открывает объект источника данных с помощью компонентов службы в oledb32.dll. Эта DLL-библиотека содержит реализацию возможностей компонентов службы, таких как создание пулов ресурсов, автоматическое прикрепление транзакций и т. д.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDataSource](../../data/oledb/cdatasource-class.md)