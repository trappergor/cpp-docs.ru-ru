---
title: "CCommand::Create | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CCommand.Create
- CCommand::Create
dev_langs: C++
helpviewer_keywords: Create method [C++]
ms.assetid: e4bede7a-68bd-491a-97f4-89b03d45cd24
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f4bbd236c2ec7ae6857ede1ac64f738ca8600774
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccommandcreate"></a>CCommand::Create
Вызовы [CCommand::CreateCommand](../../data/oledb/ccommand-createcommand.md) для создания команды для указанного сеанса, затем вызывает метод [ICommandText::SetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) для задания текста команды.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT CCommandBase::Create(  
   const CSession& session,   
   LPCWSTR wszCommand,   
   REFGUID guidCommand = DBGUID_DEFAULT  
) throw ( );  
HRESULT CCommandBase::Create(  
   const CSession& session,   
   LPCSTR szCommand,   
   REFGUID guidCommand = DBGUID_DEFAULT  
) throw ( );  
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