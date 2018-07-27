---
title: Операции ввода и вывода для консоли и портов | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.io
dev_langs:
- C++
helpviewer_keywords:
- routines, console and port I/O
- routines
- ports, I/O routines
- I/O [CRT], console
- I/O [CRT], port
- I/O routines, console and port I/O
ms.assetid: 0eee1c92-9b3d-41e0-a43a-257e546eeec8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e4d46582266234b4208a768fc7b2045af824349
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391422"
---
# <a name="console-and-port-io"></a>Ввод-вывод на консоль и порт

Эти процедуры выполняют чтение и запись для консоли или порта с определенным номером. Процедуры ввода и вывода для консоли не совместимы с библиотечными процедурами потокового или низкоуровневого ввода-вывода. В этой категории не представлены процедуры для открытия или закрытия консоли или портов, поскольку нет необходимости выполнять их перед операциями ввода-вывода. В операционных системах Windows выходные данные этих функций всегда направляются в консоль, и у вас нет возможности перенаправить их.

## <a name="console-and-port-io-routines"></a>Подпрограммы ввода и вывода для консоли и портов

|Подпрограмма|Использовать|
|-------------|---------|
|[_cgets, _cgetws](../c-runtime-library/cgets-cgetws.md), [_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)|Считывание строки из консоли|
|[_cprintf, _cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md), [_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l](../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)|Вывод форматированных данных на консоль|
|[_cputs](../c-runtime-library/reference/cputs-cputws.md)|Вывод строки на консоль|
|[_cscanf, _cwscanf](../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md), [_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l](../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)|Считывание форматированных данных из консоли|
|[_getch, _getwch](../c-runtime-library/reference/getch-getwch.md)|Считывание символа из консоли|
|[_getche, _getwche](../c-runtime-library/reference/getch-getwch.md)|Считывание и отображение символа из консоли|
|[_inp](../c-runtime-library/inp-inpw-inpd.md)|Считывание одного байта из указанного порта ввода-вывода|
|[_inpd](../c-runtime-library/inp-inpw-inpd.md)|Считывание двойного слова из указанного порта ввода-вывода|
|[_inpw](../c-runtime-library/inp-inpw-inpd.md)|Считывание двухбайтового слова из указанного порта ввода-вывода|
|[_kbhit](../c-runtime-library/reference/kbhit.md)|Проверка нажатия клавиш в консоли, которую следует выполнять перед попыткой чтения из консоли|
|[_outp](../c-runtime-library/outp-outpw-outpd.md)|Запись одного байта в указанный порт ввода-вывода|
|[_outpd](../c-runtime-library/outp-outpw-outpd.md)|Запись двойного слова в указанный порт ввода-вывода|
|[_outpw](../c-runtime-library/outp-outpw-outpd.md)|Запись слова в указанный порт ввода-вывода|
|[_putch, _putwch](../c-runtime-library/reference/putch-putwch.md)|Запись символа в консоль|
|[_ungetch, _ungetwch](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)|"Отмена чтения" последнего символа, полученного из консоли, чтобы он стал следующим символом для считывания|

## <a name="see-also"></a>См. также

[Ввод и вывод](../c-runtime-library/input-and-output.md)<br/>
 [Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)<br/>