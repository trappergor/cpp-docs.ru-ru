---
title: Ошибка средств компоновщика LNK4020 предупреждение | Документы Microsoft
ms.custom: ''
ms.date: 05/29/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4020
dev_langs:
- C++
helpviewer_keywords:
- LNK4020
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e55239b90910f6c151949c53939d4f8ed7c15c5
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34570708"
---
# <a name="linker-tools-warning-lnk4020"></a>Предупреждение средств компоновщика LNK4020

> запись типа в "*filename*" повреждена; некоторые символы и типы могут быть недоступными из отладчика

PDB-файл *filename* есть запись поврежденный тип.

Эта проблема часто является вторичной для других проблем сборки; Если это в первую очередь построения отчета, работать с другим ошибкам и предупреждениям первой. Если это первый выявленной ошибки, может потребоваться очистить каталоги сборки и заново постройте проект. Если вы используете процессы параллельные сборки, см. Если ошибка не устранена, при сериализации сборки.