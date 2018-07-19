---
title: Ошибка средств компоновщика LNK2023 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2023
dev_langs:
- C++
helpviewer_keywords:
- LNK2023
ms.assetid: c99e35a8-739a-4a20-a715-29b8c3744703
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b53fba3743d6d072930e430c15b79e0e31d68d2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302611"
---
# <a name="linker-tools-error-lnk2023"></a>Ошибка средств компоновщика LNK2023
Неверная библиотека dll или точка входа \<dll или точка входа >  
  
 Компоновщик загружается неправильная версия библиотеки msobj90.dll. Убедитесь, что link.exe и библиотеки msobj90.dll в пути имеют ту же версию.  
  
 Возможно, отсутствует зависимость от библиотеки msobj90.dll. Ниже приведен список зависимостей для библиотеки msobj90.dll.  
  
-   Msvcr90.dll  
  
-   Kernel32.dll  
  
 Проверьте свой компьютер и другие копии библиотеки msobj90.dll, которые могут быть устаревшими.