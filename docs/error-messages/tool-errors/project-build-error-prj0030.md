---
title: "Ошибка построения проекта PRJ0030 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0030
dev_langs:
- C++
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b6fe537dd8e6705fd5e30929a2480eb1d9ef9119
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0030"></a>Ошибка построения проекта PRJ0030
Ошибка расширения макроса. Оцените рекурсии превышает 32 уровней для $(макрос).  
  
 Эта ошибка вызвана рекурсии в макросе. Например, если задать **промежуточный каталог** свойство (в разделе [свойств «Общие» (проект)](../../ide/general-property-page-project.md)) значение $(IntDir), то будет возникать рекурсия.  
  
 Чтобы устранить эту ошибку, не следует определять макросы или свойства с помощью макросов, в котором они используются для определения.