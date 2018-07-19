---
title: Ошибка построения проекта PRJ0030 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0030
dev_langs:
- C++
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1bf1c9137f8c4ed0d80955eef38b07ea86204a5c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33317662"
---
# <a name="project-build-error-prj0030"></a>Ошибка построения проекта PRJ0030
Ошибка расширения макроса. Оцените рекурсии превышает 32 уровней для $(макрос).  
  
 Эта ошибка вызвана рекурсии в макросе. Например, если задать **промежуточный каталог** свойство (в разделе [свойств «Общие» (проект)](../../ide/general-property-page-project.md)) значение $(IntDir), то будет возникать рекурсия.  
  
 Чтобы устранить эту ошибку, не следует определять макросы или свойства с помощью макросов, в котором они используются для определения.