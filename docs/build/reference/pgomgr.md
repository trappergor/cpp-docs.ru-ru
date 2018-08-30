---
title: pgomgr | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- pgomgr program
- profile-guided optimizations, pgomgr
ms.assetid: 74589126-df18-42c9-8739-26d60e148d6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70a0615debabb056110dd9d6f7a6aac86e9d464a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43198319"
---
# <a name="pgomgr"></a>pgomgr

Добавление профиля данных из одного или нескольких файлов .pgc в PGD-файл.

## <a name="syntax"></a>Синтаксис

> **pgomgr** [*параметры*] *pgcfiles* *pgdfile*

### <a name="parameters"></a>Параметры

*Параметры*<br/>
Можно указать следующие параметры для **pgomgr**:

- **/ help** или **/?** Выводит доступную **pgomgr** параметры.

- **/ clear** вызывает PGD-файл очистить все данные профиля. Нельзя указать .pgc файла, когда **/clear** указан.

- **/ detail** отображает подробную статистику, включая данные о покрытии граф потока.

- **/ summary** отображает каждой функции статистики.

- **/ unique** при использовании с **/summary**, внутренних имен функций для отображения. Значение по умолчанию, когда **/ unique** не используется, для имен объявление функции для отображения.

- **/ merge**\[**:**<em>n</em>] вызывает запись данных в PGC-файл или файлы для добавления в PGD-файл. Необязательный параметр, *n*, позволяет указать, что данные должны быть добавлены *n* раз. Например, если сценарий должен done шесть раз для отражения, как часто он выполняется с клиентов, можно сделать всего один раз в тестовом запуске и добавить его в PGD-файл в шесть раз с **pgomgr /merge:6**.

*pgcfiles*<br/>
Один или несколько PGC-файлы, данные профиля, которые необходимо объединить в PGD-файла. Можно указать один или несколько файлов .pgc. Если вы не укажете все файлы .pgc **pgomgr** объединяет все файлы .pgc, имена которых совпадают с PGD-файла.

*pgdFile* PGD-файла, в который при объединении данных из PGC-файл или файлы.

## <a name="remarks"></a>Примечания

> [!NOTE]
> Это средство можно запустить только из командной строки разработчика Visual Studio. В системной командной строке или проводнике это невозможно.

## <a name="example"></a>Пример

В этом примере команда удаляет файл myapp.pgd данных профиля:

`pgomgr /clear myapp.pgd`

В этом примере команда добавляет данные профиля в файле myapp1.pgc в PGD-файл трижды:

`pgomgr /merge:3 myapp1.pgc myapp.pgd`

В этом примере файл myapp.pgd добавляется профиль данных из всех файлов myapp # .pgc.

`pgomgr -merge myapp1.pgd`

## <a name="see-also"></a>См. также

[Профильная оптимизация](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
[pgosweep](pgosweep.md)<br/>
