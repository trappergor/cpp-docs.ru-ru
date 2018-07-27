---
title: Ошибка средств компоновщика LNK2017 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2017
dev_langs:
- C++
helpviewer_keywords:
- LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 095423b5f2d86cef309ed4316ff72d195b11eb26
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33313076"
---
# <a name="linker-tools-error-lnk2017"></a>Ошибка средств компоновщика LNK2017
«Символ» перемещения для «сегмент» недопустимый без: No  
  
 Вы пытаетесь создать образ x 64 с 32-разрядными адресами. Чтобы сделать это, необходимо выполнить следующее:  
  
-   Используйте фиксированный адрес загрузки.  
  
-   Ограничьте размер изображения до 3 ГБ.  
  
-   Укажите [: no](../../build/reference/largeaddressaware-handle-large-addresses.md).