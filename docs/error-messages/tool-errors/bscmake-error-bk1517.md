---
title: "Ошибка BSCMAKE BK1517 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: BK1517
dev_langs: C++
helpviewer_keywords: BK1517
ms.assetid: 24391f42-0a3e-40a9-9991-c8b9a6a7b1c7
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5978ceab4a5a5e768ddda635398466bb941c42cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-error-bk1517"></a>Ошибка BSCMAKE BK1517
исходный SBR-файл скомпилирован с параметрами /Yc и /Yu  
  
 SBR-файл ссылается само на себя. Возможно, он был перекомпилирован с параметром /Yu после компиляции с параметром/Yc. Восстановите /Yc параметр компилятора для исходного файла, а затем выберите **Перестроить** , чтобы создать новый SBR-файлы. Не перекомпилируйте исходный файл с /Yu.