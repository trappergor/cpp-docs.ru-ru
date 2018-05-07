---
title: DEFINE_COMMAND | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- DEFINE_COMMAND
dev_langs:
- C++
helpviewer_keywords:
- DEFINE_COMMAND macro
ms.assetid: 9d724968-e242-413c-9a13-e7175fccf9b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 51f975b0477d29fbb35880c796f52612456c32c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="definecommand"></a>DEFINE_COMMAND
Задает команду, которая будет использоваться для создания набора строк при использовании [CCommand](../../data/oledb/ccommand-class.md) класса. Принимает только строковые типы, совпадающим с типом указанного приложения (ANSI или Юникод).  
  
> [!NOTE]
>  Рекомендуется использовать [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) вместо `DEFINE_COMMAND`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
DEFINE_COMMAND(x, szCommand)  
  
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