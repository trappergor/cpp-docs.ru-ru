---
title: Экспорт функций из библиотеки DLL по порядковому номеру, а не по имени
ms.date: 11/04/2016
helpviewer_keywords:
- exporting functions [C++], ordinal values
- ordinal exports [C++]
- exporting DLLs [C++], ordinal values
- NONAME attribute
ms.assetid: 679719fd-d965-4df3-9f7a-7d86ad831702
ms.openlocfilehash: 66e99b18d181e9067e90398c35a61db2da66c301
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328578"
---
# <a name="exporting-functions-from-a-dll-by-ordinal-rather-than-by-name"></a>Экспорт функций из библиотеки DLL по порядковому номеру, а не по имени

Самый простой способ экспортировать функции из Вашего DLL — экспортировать их по имени. Это то, что происходит, когда вы используете **__declspec (dllexport),** например. Но вместо этого вы можете экспортировать функции по ординатору. С помощью этого метода, вы должны использовать файл .def вместо **__declspec (dllexport)**. Чтобы указать ординальное значение функции, приспособите ее обыденое к имени функции в файле .def. Для получения информации об указании ординалов [см. Экспорт из DLL с помощью файлов .def](exporting-from-a-dll-using-def-files.md).

> [!TIP]
> Если вы хотите оптимизировать размер файла DLL, используйте атрибут **NONAME** на каждой экспортируемой функции. С атрибутом **NONAME** ординаторы хранятся в таблице экспорта DLL, а не в названиях функций. Это может быть значительная экономия, если вы экспортируете много функций.

## <a name="what-do-you-want-to-do"></a>Выбор действия

- [Используйте файл .def, чтобы я мог экспортировать по ординатору](exporting-from-a-dll-using-def-files.md)

- [Используйте __declspec (dllexport)](exporting-from-a-dll-using-declspec-dllexport.md)

## <a name="see-also"></a>См. также раздел

[Экспорт из библиотеки DLL](exporting-from-a-dll.md)
