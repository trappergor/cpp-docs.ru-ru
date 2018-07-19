---
title: Ошибка средств компоновщика LNK1188 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1188
dev_langs:
- C++
helpviewer_keywords:
- LNK1188
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e31943ae253a332576fba73102db410b103a0096
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302624"
---
# <a name="linker-tools-error-lnk1188"></a>Ошибка средств компоновщика LNK1188
BADFIXUPSECTION:: недопустимая адресная привязка целевой «символ»; Возможные раздел нулевой длины  
  
 Во время компоновки VxD целевым объектом переадресации отсутствует раздел. С LINK386 (устаревшая версия), возможно, запись OMF GROUP (созданных в ходе директивы MASM GROUP) был использован для объединения раздел нулевой длины с другой раздел ненулевой длины. Формат COFF не поддерживает директивы GROUP и разделы нулевой длины. Эта ошибка может возникать, когда программа LINK автоматически преобразует этот тип объектов OMF в формат COFF.