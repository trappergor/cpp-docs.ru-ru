---
title: Экспорт функций из библиотеки DLL по порядковому номеру, а не по имени
ms.date: 11/04/2016
helpviewer_keywords:
- exporting functions [C++], ordinal values
- ordinal exports [C++]
- exporting DLLs [C++], ordinal values
- NONAME attribute
ms.assetid: 679719fd-d965-4df3-9f7a-7d86ad831702
ms.openlocfilehash: d91b516253fc160686e2f1f6ae1ca1704f707f75
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221426"
---
# <a name="exporting-functions-from-a-dll-by-ordinal-rather-than-by-name"></a>Экспорт функций из библиотеки DLL по порядковому номеру, а не по имени

Экспорт функций из библиотеки DLL проще экспортировать их по имени. Это происходит при использовании **__declspec(dllexport)**, например. Но можно также экспортировать функции по порядковому номеру. С помощью этого способа необходимо использовать DEF-файл, а не **__declspec(dllexport)**. Чтобы указать порядковый номер функции, добавьте номер к имени функции в DEF-файле. Сведения об указании порядковых номеров см. в разделе [Экспорт из DLL с использованием DEF-файлы](exporting-from-a-dll-using-def-files.md).

> [!TIP]
>  Если вы хотите оптимизировать размер файла библиотеки DLL, используйте **NONAME** атрибута для каждой экспортируемой функции. С помощью **NONAME** атрибут, порядковые номера хранятся в библиотеки DLL экспортировать таблицу, а не имена функций. Это может быть значительную экономию при экспорте множество функций.

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Использовать DEF-файла для экспорта по порядковому номеру](exporting-from-a-dll-using-def-files.md)

- [Use __declspec(dllexport)](exporting-from-a-dll-using-declspec-dllexport.md)

## <a name="see-also"></a>См. также

[Экспорт из библиотеки DLL](exporting-from-a-dll.md)
