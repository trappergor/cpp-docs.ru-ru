---
title: "Ошибка средств компоновщика LNK1188 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1188
dev_langs:
- C++
helpviewer_keywords:
- LNK1188
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 81d2988742eb9e8cd6aef134510ac8272d3dd27c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1188"></a>Ошибка средств компоновщика LNK1188
BADFIXUPSECTION:: недопустимая адресная привязка целевой «символ»; Возможные раздел нулевой длины  
  
 Во время компоновки VxD целевым объектом переадресации отсутствует раздел. С LINK386 (устаревшая версия), возможно, запись OMF GROUP (созданных в ходе директивы MASM GROUP) был использован для объединения раздел нулевой длины с другой раздел ненулевой длины. Формат COFF не поддерживает директивы GROUP и разделы нулевой длины. Эта ошибка может возникать, когда программа LINK автоматически преобразует этот тип объектов OMF в формат COFF.