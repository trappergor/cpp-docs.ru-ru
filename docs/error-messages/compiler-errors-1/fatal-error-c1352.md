---
title: "Неустранимая ошибка C1352 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1352
dev_langs: C++
helpviewer_keywords: C1352
ms.assetid: d044e8b0-b6ef-4d57-8eb5-6254071be707
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2f2a5c42eaa5afc609f1b8ee1c09875db8bff9c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1352"></a>Неустранимая ошибка C1352
Недопустимый или поврежденный блок MSIL в функции "функция" из модуля "файл"  
  
 Компилятору передан файл NETMODULE, но компилятор обнаружил поврежденный элемент файла.  Для получения сведений обратитесь к создателю файла NETMODULE.  
  
 Компилятор выполняет проверку наличия не всех типов повреждений в файлах NETMODULE.  Однако он проверяет все пути выполнения в функции на наличие оператора return.  
  
 Дополнительные сведения см. в разделе [NETMODULE-файлы в качестве входных файлов компоновщика](../../build/reference/netmodule-files-as-linker-input.md).