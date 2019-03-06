---
title: Параметры EDITBIN
ms.date: 11/04/2016
f1_keywords:
- editbin
helpviewer_keywords:
- EDITBIN program, options
ms.assetid: 2da9f88e-cbab-4d64-bb66-ef700535230f
ms.openlocfilehash: 409c40986068475299c95f1be0dff5f15d022520
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57424331"
---
# <a name="editbin-options"></a>Параметры EDITBIN

(Программа EDITBIN) можно использовать для изменения объектных файлов, исполняемых файлов и библиотек динамической компоновки (DLL). Параметры указывают изменения, сделанные (программа EDITBIN).

Параметр состоит из спецификатора, которое может быть дефисом (-) или косой черты (/), за которым следует имя параметра. Имена параметров не может быть сокращены. Некоторые параметры принимают аргументы, указанные после двоеточия (:). Внутри параметра допускаются пробелы или табуляцию. Используйте один или несколько пробелов или вкладки следует разделять в командной строке. Имена параметров и их аргументы ключевое слово или имя файла аргументов не учитывают регистр. Например, - привязки и средства означает то же.

(Программа EDITBIN) имеет следующие параметры:

|Параметр|Цель|
|------------|-------------|
|[/ALLOWBIND](../../build/reference/allowbind.md)|Указывает, можно ли привязать библиотеку DLL.|
|[/ALLOWISOLATION](../../build/reference/allowisolation.md)|Указывает библиотеку DLL или поведение поиск манифеста в исполняемый файл.|
|[/APPCONTAINER](../../build/reference/appcontainer.md)|Указывает, должно ли приложение работать в AppContainer — например, приложение UWP.|
|[/BIND](../../build/reference/bind.md)|Задает адреса для точки входа в указанных объектов, чтобы сократить время загрузки.|
|[/DYNAMICBASE](../../build/reference/dynamicbase.md)|Указывает ли библиотеки DLL или исполняемый образ может быть случайным образом переместить во время загрузки, используя технологию address space макета randomization (ASLR).|
|[/ ERRORREPORT](../../build/reference/errorreport-editbin-exe.md)|Отчеты о внутренних ошибках в корпорацию Майкрософт.|
|[/HEAP](../../build/reference/heap.md)|Задает размер кучи исполняемый образ, в байтах.|
|[/HIGHENTROPYVA](../../build/reference/highentropyva.md)|Указывает, поддерживает ли библиотеки DLL или исполняемый образ файлами технологии с высокой энтропией (64-разрядная версия) адрес space layout randomization (ASLR).|
|[/INTEGRITYCHECK](../../build/reference/integritycheck.md)|Указывает, нужно ли проверять цифровую подпись при загрузке.|
|[/LARGEADDRESSAWARE](../../build/reference/largeaddressaware.md)|Указывает, поддерживает ли объект адреса, превышающие два гигабайта.|
|[/NOLOGO](../../build/reference/nologo-editbin.md)|Отключает загрузочный баннер (программа EDITBIN).|
|[/NXCOMPAT](../../build/reference/nxcompat.md)|Указывает, совместим ли исполняемый образ с предотвращением выполнения данных Windows.|
|[/REBASE](../../build/reference/rebase.md)|Задает базовые адреса для указанных объектов.|
|[/RELEASE](../../build/reference/release.md)|Задает контрольную сумму в заголовке.|
|[/SECTION](../../build/reference/section-editbin.md)|Переопределяет атрибуты секции.|
|[/STACK](../../build/reference/stack.md)|Задает размер стека исполняемый образ, в байтах.|
|[/SUBSYSTEM](../../build/reference/subsystem.md)|Указывает среде выполнения.|
|[/SWAPRUN](../../build/reference/swaprun.md)|Указывает исполняемый образ должен скопировать файл подкачки и запустите оттуда.|
|[/TSAWARE](../../build/reference/tsaware.md)|Указывает, что приложение, предназначенное для работы в многопользовательской среде.|
|[/VERSION](../../build/reference/version.md)|Задает номер версии в заголовке.|

## <a name="see-also"></a>См. также

[Средства сборки С/C++](../../build/reference/c-cpp-build-tools.md)<br/>
[Справочник ЕDITBIN](../../build/reference/editbin-reference.md)
