---
title: Ошибка построения проекта PRJ0003 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0003
dev_langs:
- C++
helpviewer_keywords:
- PRJ0003
ms.assetid: fc5a84bb-c6d3-41d6-8dd6-475455820778
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a44f272569741b1897caed1d1d64832d8b113eae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33316440"
---
# <a name="project-build-error-prj0003"></a>Ошибка построения проекта PRJ0003  
  
> Создание ошибки "*командной строки*".  
  
*Командной строки* команда сформирован на основе входных данных в **страницы свойств** диалоговое окно вернул код ошибки, но не отображаются данные в **вывода** окна.  

Возможные причины этой ошибки включают:  
  
-   Проект зависит от библиотеки ATL Server. Начиная с Visual Studio 2008, сервер ATL больше не включены в Visual Studio, но была выпущена в виде проекта общий источник на CodePlex. Чтобы загрузить исходный код для ATL-сервера и средств, перейдите на [ATL-сервера библиотеки и средства](http://go.microsoft.com/fwlink/p/?linkid=81979).  
  
-   Нехватка системных ресурсов. Закройте некоторые приложения для решения этой проблемы.  
  
-   Недостаточные привилегии безопасности. Убедитесь, что у вас достаточно прав безопасности.  
  
-   Пути к исполняемым файлам, указанный в **каталоги VC ++** должно содержать путь, предпринимается попытка запуска программы. Сведения см. в разделе [работа со свойствами проектов](../../ide/working-with-project-properties.md)  
  
-   В проектах makefile отсутствует команда на выполнение в **командной строке для построения** или **командной строке перестроения**.  
  
## <a name="see-also"></a>См. также  
 [Ошибки и предупреждения режима сборки проекта (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)