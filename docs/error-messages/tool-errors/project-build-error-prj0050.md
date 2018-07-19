---
title: Ошибка построения проекта PRJ0050 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0050
dev_langs:
- C++
helpviewer_keywords:
- PRJ0050
ms.assetid: ceef3b37-0acf-4abd-ac62-aa830b4fa145
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ad17614f693e313190dba9cc767c023981dec34
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33318517"
---
# <a name="project-build-error-prj0050"></a>Ошибка построения проекта PRJ0050
Не удалось зарегистрировать выход. Убедитесь, что имеются соответствующие разрешения на изменение реестра.  
  
 Система построения Visual C++ не удалось зарегистрировать выходной файл сборки (dll или .exe). Необходимо войти в систему с правами администратора, чтобы внести изменения в реестр.  
  
 При создании библиотеки DLL можно попробовать зарегистрировать DLL-файл вручную с помощью regsvr32.exe, после этого должен отобразиться сведения о причинах сбоя.  
  
 При построении не DLL-файл, просмотрите журнал сборки для команды, которая вызывает ошибку.