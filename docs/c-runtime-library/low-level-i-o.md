---
title: Низкоуровневый ввод-вывод
ms.date: 11/04/2016
f1_keywords:
- c.io
helpviewer_keywords:
- I/O [CRT], low-level
- I/O [CRT], functions
- low-level I/O routines
- file handles [C++]
- file handles [C++], I/O functions
ms.assetid: 53e11bdd-6720-481c-8b2b-3a3a569ed534
ms.openlocfilehash: 25a61fd7bd033accbbae11fafbd44a0282649e8e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656928"
---
# <a name="low-level-io"></a>Низкоуровневый ввод-вывод

Эти функции напрямую обращаются к операционной системе для выполнения операций более низкого уровня, чем при потоковом вводе-выводе. Операции низкоуровневого ввода и вывода не поддерживают буферизацию или форматирование данных.

Низкоуровневые процедуры могут обращаться к стандартным потокам, открытым при запуске программы, с помощью следующих стандартных дескрипторов файла.

|Поток|Дескриптор файла|
|------------|---------------------|
|**stdin**|0|
|**stdout**|1|
|**stderr**|2|

Набор подпрограмм низкоуровневого ввода-вывода при возникновении ошибки устанавливает глобальную переменную [errno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). При использовании низкоуровневых функций библиотеку STDIO.H нужно включать только в том случае, если программе требуется константа, определенная в STDIO.H, например индикатор конца файла (**EOF**).

## <a name="low-level-io-functions"></a>Процедуры низкоуровневого ввода и вывода

|Функция|Использовать|
|--------------|---------|
|[_close](../c-runtime-library/reference/close.md)|Закрывает файл|
|[_commit](../c-runtime-library/reference/commit.md)|Сбрасывает файл на диск|
|[_creat, _wcreat](../c-runtime-library/reference/creat-wcreat.md)|Создает файл|
|[_dup](../c-runtime-library/reference/dup-dup2.md)|Возвращает следующий доступный дескриптор файла для указанного файла|
|[_dup2](../c-runtime-library/reference/dup-dup2.md)|Создает второй дескриптор для указанного файла|
|[_eof](../c-runtime-library/reference/eof.md)|Проверяет достижение конца файла|
|[_lseek, _lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)|Перемещает указатель файла в указанное положение|
|[_open, _wopen](../c-runtime-library/reference/open-wopen.md)|Открывает файл|
|[_read](../c-runtime-library/reference/read.md)|Считывает данные из файла|
|[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md), [_sopen_s, _wsopen_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|Открывает файл для совместного использования|
|[_tell, _telli64](../c-runtime-library/reference/tell-telli64.md)|Получает текущую позицию указателя файла|
|[_umask](../c-runtime-library/reference/umask.md), [_umask_s](../c-runtime-library/reference/umask-s.md)|Задает маску разрешений для файла|
|[_write](../c-runtime-library/reference/write.md)|Записывает данные в файл|

Обычно **_dup** и **_dup2** используются для связи предопределенных дескрипторов файлов с разными файлами.

## <a name="see-also"></a>См. также

[Ввод и вывод](../c-runtime-library/input-and-output.md)<br/>
[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Системные вызовы](../c-runtime-library/system-calls.md)<br/>
