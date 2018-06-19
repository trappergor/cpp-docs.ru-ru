---
title: Параметры EDITBIN | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- editbin
dev_langs:
- C++
helpviewer_keywords:
- EDITBIN program, options
ms.assetid: 2da9f88e-cbab-4d64-bb66-ef700535230f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1922e410b0151337ce403e24d20ae90b7e964cd5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378526"
---
# <a name="editbin-options"></a>Параметры EDITBIN
EDITBIN можно использовать для изменения объектных файлов, исполняемых файлов и библиотек динамической компоновки (DLL). Параметры определяют изменения, которые вносит EDITBIN.  
  
 Параметр состоит из спецификатора дефис (-) или косой черты (/), за которым следует имя параметра. Имена параметров не сокращается. Некоторые параметры принимают аргументы, указанные после двоеточия (:). В спецификации параметра допускаются пробелы или табуляцию. Используйте один или несколько пробелов или вкладки следует разделять в командной строке. Имена параметров и их аргументы ключевое слово или имя файла аргументов не учитывают регистр. Например, - привязки и/BIND взаимозаменяемыми.  
  
 EDITBIN имеет следующие параметры:  
  
|Параметр|Цель|  
|------------|-------------|  
|[/ALLOWBIND](../../build/reference/allowbind.md)|Указывает, можно ли привязать библиотеку DLL.|  
|[/ALLOWISOLATION](../../build/reference/allowisolation.md)|Указывает, библиотеки DLL или исполняемого файла поведение нахождения файлов манифеста.|  
|[/APPCONTAINER](../../build/reference/appcontainer.md)|Указывает, должно ли приложение выполняться в AppContainer — например, приложения UWP.|  
|[/BIND](../../build/reference/bind.md)|Задает адреса для точки входа в указанные объекты в скорости время загрузки.|  
|[/DYNAMICBASE](../../build/reference/dynamicbase.md)|Указывает, является ли DLL или исполняемого образа может быть случайным образом перемещен во время загрузки, используя технологию address space макета randomization (ASLR).|  
|[/ ERRORREPORT](../../build/reference/errorreport-editbin-exe.md)|Отчеты о внутренних ошибках в корпорацию Майкрософт.|  
|[/HEAP](../../build/reference/heap.md)|Задает размер кучи исполняемый образ, в байтах.|  
|[/HIGHENTROPYVA](../../build/reference/highentropyva.md)|Указывает, поддерживает ли DLL или исполняемого образа с высокой энтропией (64-разрядная версия) адрес пространства макета randomization (ASLR).|  
|[/INTEGRITYCHECK](../../build/reference/integritycheck.md)|Указывает, следует ли проверять цифровую подпись во время загрузки.|  
|[/LARGEADDRESSAWARE](../../build/reference/largeaddressaware.md)|Указывает, поддерживает ли объект адреса, превышающие два гигабайта.|  
|[/ NOLOGO](../../build/reference/nologo-editbin.md)|Отключает загрузочный баннер EDITBIN.|  
|[/NXCOMPAT](../../build/reference/nxcompat.md)|Указывает, совместим ли исполняемый образ с предотвращением исполнения данных Windows.|  
|[/REBASE](../../build/reference/rebase.md)|Задает базовые адреса для указанных объектов.|  
|[/RELEASE](../../build/reference/release.md)|Задает контрольную сумму в заголовке.|  
|[/ SECTION](../../build/reference/section-editbin.md)|Переопределяет атрибуты секции.|  
|[/STACK](../../build/reference/stack.md)|Задает размер стека исполняемый образ, в байтах.|  
|[/SUBSYSTEM](../../build/reference/subsystem.md)|Указывает среду выполнения.|  
|[/SWAPRUN](../../build/reference/swaprun.md)|Указывает исполняемый образ необходимо копируются в файл подкачки, а затем выполнить оттуда.|  
|[/TSAWARE](../../build/reference/tsaware.md)|Указывает, что приложение, предназначенное для работы в многопользовательской среде.|  
|[/VERSION](../../build/reference/version.md)|Задает номер версии в заголовке.|  
  
## <a name="see-also"></a>См. также  
 [Средства построения C/C++](../../build/reference/c-cpp-build-tools.md)   
 [Справочник ЕDITBIN](../../build/reference/editbin-reference.md)