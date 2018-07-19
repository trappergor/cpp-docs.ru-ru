---
title: Экспорт функций из библиотеки DLL по порядковому номеру, а не по имени | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- NONAME
dev_langs:
- C++
helpviewer_keywords:
- exporting functions [C++], ordinal values
- ordinal exports [C++]
- exporting DLLs [C++], ordinal values
- NONAME attribute
ms.assetid: 679719fd-d965-4df3-9f7a-7d86ad831702
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b05f3e429406b3c24c7a21ce9ee8e10fe19c14b8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367697"
---
# <a name="exporting-functions-from-a-dll-by-ordinal-rather-than-by-name"></a>Экспорт функций из библиотеки DLL по порядковому номеру, а не по имени
Самый простой способ экспорта функций из библиотеки DLL будет экспортировать их по имени. Вот что происходит при использовании **__declspec(dllexport)**, например. Однако можно также экспортировать функции по порядковому номеру. С помощью этого метода необходимо использовать DEF-файл, а не **__declspec(dllexport)**. Чтобы указать порядковый номер функции, добавьте номер к имени функции в DEF-файл. Сведения об указании порядковых номеров см. в разделе [Экспорт из библиотеки DLL с использованием DEF-файлы](../build/exporting-from-a-dll-using-def-files.md).  
  
> [!TIP]
>  Если вы хотите оптимизировать размер файла библиотеки DLL, используйте **NONAME** атрибута для каждой экспортируемой функции. С **NONAME** атрибут, порядковые номера, хранятся в экспорта библиотеки DLL, таблицы, а не имена функций. Это может быть существенно экономит множество функций для экспорта.  
  
## <a name="what-do-you-want-to-do"></a>Выберите действие  
  
-   [Используйте DEF-файла для экспорта по порядковому номеру](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Используйте __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
## <a name="see-also"></a>См. также  
 [Экспорт из библиотеки DLL](../build/exporting-from-a-dll.md)