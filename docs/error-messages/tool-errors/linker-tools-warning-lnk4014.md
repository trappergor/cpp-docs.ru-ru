---
title: Предупреждение средств компоновщика LNK4014
ms.date: 11/04/2016
f1_keywords:
- LNK4014
helpviewer_keywords:
- LNK4014
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
ms.openlocfilehash: f67990ed74f500f1b954edcf1d6437f64f93f0d6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511716"
---
# <a name="linker-tools-warning-lnk4014"></a>Предупреждение средств компоновщика LNK4014

не удается найти объект члена «objectname»

Не удалось найти LIB `objectname` в библиотеке.

**/REMOVE** и **/EXTRACT** параметров необходимо полное имя объекта-члена, удалить или скопировать в файл. Полное имя включает в себя путь исходного файла объекта. Для просмотра полных имен объектов-членов в библиотеке, использование служебной программы DUMPBIN [/ARCHIVEMEMBERS](../../build/reference/archivemembers.md) или LIB [/LIST](../../build/reference/managing-a-library.md).