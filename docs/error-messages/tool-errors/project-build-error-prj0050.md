---
title: "Ошибка построения проекта PRJ0050 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0050
dev_langs: C++
helpviewer_keywords: PRJ0050
ms.assetid: ceef3b37-0acf-4abd-ac62-aa830b4fa145
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e9d9b123da2e32db0f695c31bc9643a481d352b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0050"></a>Ошибка построения проекта PRJ0050
Не удалось зарегистрировать выход. Убедитесь, что имеются соответствующие разрешения на изменение реестра.  
  
 Система построения Visual C++ не удалось зарегистрировать выходной файл сборки (dll или .exe). Необходимо войти в систему с правами администратора, чтобы внести изменения в реестр.  
  
 При создании библиотеки DLL можно попробовать зарегистрировать DLL-файл вручную с помощью regsvr32.exe, после этого должен отобразиться сведения о причинах сбоя.  
  
 При построении не DLL-файл, просмотрите журнал сборки для команды, которая вызывает ошибку.