---
title: "CCommand::GetNextResult | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CCommand::GetNextResult
- CCommand::GetNextResult
- GetNextResult
- CCommand.GetNextResult
- ATL.CCommand.GetNextResult
dev_langs: C++
helpviewer_keywords: GetNextResult method
ms.assetid: 63df9b55-9490-45c4-934a-879c5c2725d8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a3bf105f0c85d831d1a8e4bb0048a1385e6275da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccommandgetnextresult"></a>CCommand::GetNextResult
Извлекает следующий результирующий набор, если он доступен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT GetNextResult(  
   DBROWCOUNT* pulRowsAffected,  
   bool bBind = true   
) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 *pulRowsAffected*  
 [входные/выходные] Указатель на область памяти, где возвращается число строк, затронутых командой.  
  
 `bBind`  
 [in] Указывает, нужно ли привязывать команда автоматически после выполнения. Значение по умолчанию — **true**, что вызывает команду, чтобы автоматически привязать. Установка `bBind` для **false** предотвращает автоматическое привязку команды, таким образом, можно привязать вручную. (Ручной привязки — особый интерес для пользователей OLAP).  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Если результирующий набор ранее извлечены, эта функция освобождает предыдущий результирующий набор и отменяет привязку столбцов по. Если `bBind` — **true**, он выполняет привязку новых столбцов.  
  
 Эту функцию следует вызывать только в том случае, если вы указали несколько результатов, задав `CCommand` параметр шаблона *тип TMultiple*=`CMultipleResults`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CCommand](../../data/oledb/ccommand-class.md)