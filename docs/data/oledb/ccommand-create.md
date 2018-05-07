---
title: CCommand::Create | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CCommand.Create
- CCommand::Create
dev_langs:
- C++
helpviewer_keywords:
- Create method [C++]
ms.assetid: e4bede7a-68bd-491a-97f4-89b03d45cd24
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f85cfd9ed9938d76c28449fae01a87d3bb81a293
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ccommandcreate"></a>CCommand::Create
Вызовы [CCommand::CreateCommand](../../data/oledb/ccommand-createcommand.md) для создания команды для указанного сеанса, затем вызывает метод [ICommandText::SetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) для задания текста команды.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT CCommandBase::Create(const CSession& session,   
   LPCWSTR wszCommand,   
   REFGUID guidCommand = DBGUID_DEFAULT) throw ();  


HRESULT CCommandBase::Create(const CSession& session,   
   LPCSTR szCommand,   
   REFGUID guidCommand = DBGUID_DEFAULT) throw ();  
```  
  
#### <a name="parameters"></a>Параметры  
 `session`  
 [in] Сеанс, для которого требуется создать команду.  
  
 `wszCommand`  
 [in] Указатель на текст в Юникоде командной строки.  
  
 `szCommand`  
 [in] Указатель на текст ANSI командной строки.  
  
 `guidCommand`  
 [in] GUID, который определяет синтаксис и общие правила для поставщика, используемого при синтаксическом анализе текста команды. Описание диалекта см. в разделе [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) в *Справочник программиста OLE DB*.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Первая форма **создать** принимает командной строки в Юникоде. Во второй форме **создать** принимает командной строки ANSI (предоставляется для обеспечения обратной совместимости с существующими приложениями ANSI).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CCommand](../../data/oledb/ccommand-class.md)