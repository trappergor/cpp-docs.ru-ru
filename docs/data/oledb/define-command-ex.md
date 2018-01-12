---
title: "DEFINE_COMMAND_EX | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DEFINE_COMMAND_EX
dev_langs: C++
helpviewer_keywords: DEFINE_COMMAND_EX macro
ms.assetid: d3e2ef20-1455-46d2-8499-8ab84bbb90a4
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 851b346c8fac955f1d82c0c43fdf75c4784ca04c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="definecommandex"></a>DEFINE_COMMAND_EX
Задает команду, которая будет использоваться для создания набора строк при использовании [CCommand](../../data/oledb/ccommand-class.md) класса. Поддерживает Юникод и ANSI приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
DEFINE_COMMAND_EX(  
x  
,   
wszCommand  
 )  
  
```  
  
#### <a name="parameters"></a>Параметры  
 *x*  
 [in] Имя класса записей (command) пользователя.  
  
 `wszCommand`  
 [in] Командной строки, который будет использоваться для создания набора строк при использовании [CCommand](../../data/oledb/ccommand-class.md).  
  
## <a name="remarks"></a>Примечания  
 Командной строки, который можно указать, будет использоваться по умолчанию, если не задан текст команды в [CCommand::Open](../../data/oledb/ccommand-open.md) метод.  
  
 Этот макрос принимает строки в Юникоде, независимо от типа приложения. Этот макрос предпочтительнее, чем [DEFINE_COMMAND](../../data/oledb/define-command.md) , так как он поддерживает Юникод и ANSI приложений.  
  
## <a name="example"></a>Пример  
 В разделе [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные функции для шаблонов объектов-получателей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)