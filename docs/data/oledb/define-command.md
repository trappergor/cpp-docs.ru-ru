---
title: "DEFINE_COMMAND | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DEFINE_COMMAND
dev_langs: C++
helpviewer_keywords: DEFINE_COMMAND macro
ms.assetid: 9d724968-e242-413c-9a13-e7175fccf9b1
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cd2acfee6bb0f28acc774774e446e9efd4a5637b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="definecommand"></a>DEFINE_COMMAND
Задает команду, которая будет использоваться для создания набора строк при использовании [CCommand](../../data/oledb/ccommand-class.md) класса. Принимает только строковые типы, совпадающим с типом указанного приложения (ANSI или Юникод).  
  
> [!NOTE]
>  Рекомендуется использовать [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) вместо `DEFINE_COMMAND`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
DEFINE_COMMAND(  
x  
,   
szCommand  
 )  
  
```  
  
#### <a name="parameters"></a>Параметры  
 *x*  
 [in] Имя класса записей (command) пользователя.  
  
 `szCommand`  
 [in] Командной строки, который будет использоваться для создания набора строк при использовании [CCommand](../../data/oledb/ccommand-class.md).  
  
## <a name="remarks"></a>Примечания  
 Командной строки, который можно указать, будет использоваться по умолчанию, если не задан текст команды в [CCommand::Open](../../data/oledb/ccommand-open.md) метод.  
  
 Этот макрос принимает строки ANSI при построении приложения как ANSI или строки в Юникоде, при построении приложения в кодировке Юникод. Рекомендуется использовать [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) вместо `DEFINE_COMMAND`, так как первый из них принимает строки в Юникоде, независимо от типа приложения ANSI или Юникод.  
  
## <a name="example"></a>Пример  
 В разделе [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные функции для шаблонов объектов-получателей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)