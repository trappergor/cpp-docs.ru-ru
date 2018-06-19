---
title: Неустранимая ошибка CVTRES CVT1100 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CVT1100
dev_langs:
- C++
helpviewer_keywords:
- CVT1100
ms.assetid: 886e88dd-5818-4b5f-84f2-d2a3d75f0aaf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32085c4c37c82567eb78f46b52bcc4a6c41daae5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302663"
---
# <a name="cvtres-fatal-error-cvt1100"></a>Неустранимая ошибка CVTRES CVT1100
Повторный ресурс — типа: тип, имя: имя, язык: язык, флаги: флаги, размер:  
  
 Данный ресурс был указан более одного раза.  
  
 Эта ошибка может возникнуть, если компоновщик создает библиотеку типов, и вы не указали [/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md) и ресурсов в проекте, использующем 1. В этом случае укажите /TLBID и укажите другой номер до 65535.