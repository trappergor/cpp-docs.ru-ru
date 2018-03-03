---
title: "Предупреждение средств компоновщика LNK4204 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4204
dev_langs:
- C++
helpviewer_keywords:
- LNK4204
ms.assetid: 14adda20-0cbe-407b-90f6-9f81c93530e2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f9b2d9611192fe4afe01d178ac3af5fcc8ccc42
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4204"></a>Предупреждение средств компоновщика LNK4204
«имя_файла» отсутствуют отладочные данные для ссылок на модуль; компоновка объекта выполняется как при отсутствии отладочных данных  
  
 PDB-файл содержит ошибочную подпись. Компоновщик продолжит компоновку объекта без отладочной информации. Может потребоваться перекомпилировать файл объекта с помощью [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) параметр.  
  
 Ошибка LNK4204 может произойти, если некоторые объекты в библиотеке ссылаются на файл, который больше не существует. Это может произойти при перестройке решения, например; файл объекта может удален и не может быть перестроен из-за ошибки компиляции. В этом случае либо компилируйте с **/Z7**, или **/Fd**, для обновления объектов для ссылки на один файл в библиотеке (который не является именем по умолчанию PDB-файла).  Дополнительные сведения см. в разделе [/Fd (имя файла базы данных программы)](../../build/reference/fd-program-database-file-name.md).  Убедитесь, что PDB-файл сохраняется с библиотекой, каждый раз при его обновлении в системе управления версиями.