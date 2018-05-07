---
title: CCommand::Close | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CCommand.Close
- CCommand::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 4da9c02c-7082-4e47-a0fa-78b546f0f7d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5723c358e0af7cf9b92952bfd843ba90577333e8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ccommandclose"></a>CCommand::Close
Освобождает метод доступа набора строк, связанный с данной командой.  
  
## <a name="syntax"></a>Синтаксис

```cpp
void Close();  
```  
  
## <a name="remarks"></a>Примечания  
 Команда использует набор строк, результат метода доступа set и (необязательно) является параметрическим (в отличие от таблиц, которые не поддерживают параметры и не обязательно является параметрическим).  
  
 При выполнении команды, необходимо вызвать оба `Close` и [ReleaseCommand](../../data/oledb/ccommand-releasecommand.md) после команды.  
  
 Если вы хотите выполнить ту же команду повторно, каждый метод доступа set результат должен освободить путем вызова `Close` перед вызовом `Execute`. В конце ряда, доступа к параметру должен освободить путем вызова `ReleaseCommand`. Другим распространенным сценарием вызов хранимой процедуры с выходными параметрами. На многих поставщиков (например, поставщик OLE DB для SQL Server) значения выходных параметров не будет доступны до выхода из метода доступа set результат. Вызовите `Close` закрыть возвращаемого набора строк и результат метода доступа set, но не параметр метода доступа, позволяя таким образом можно получить значения выходных параметров.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как можно вызвать `Close` и `ReleaseCommand` при повторном выполнении одной команды.  
  
 [!code-cpp[NVC_OLEDB_Consumer#2](../../data/oledb/codesnippet/cpp/ccommand-close_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CCommand-класс](../../data/oledb/ccommand-class.md)   
 [CCommand::ReleaseCommand](../../data/oledb/ccommand-releasecommand.md)