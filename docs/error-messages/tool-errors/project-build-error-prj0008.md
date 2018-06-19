---
title: Ошибка построения проекта PRJ0008 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0008
dev_langs:
- C++
helpviewer_keywords:
- PRJ0008
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4011a27b7e6707f9c9b4e3ed386306b00f2792cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33317649"
---
# <a name="project-build-error-prj0008"></a>Ошибка построения проекта PRJ0008
Не удалось удалить файл «файл».  
  
 **Убедитесь, что файл не открыт другим процессом и не защищен от записи.**  
  
 Во время перестроения или очистки Visual C++ удаляет все известные промежуточных и выходных файлов для сборки, а также все файлы, которые удовлетворяют требованиям подстановочный знак в **расширения для удаления при очистке** свойства [Общие Страница свойств параметров конфигурации](../../ide/general-property-page-project.md).  
  
 Эта ошибка возникает, если Visual C++ не удается удалить файл. Чтобы устранить эту ошибку, убедитесь в файл и каталог для записи для пользователя, выполняющего сборки.