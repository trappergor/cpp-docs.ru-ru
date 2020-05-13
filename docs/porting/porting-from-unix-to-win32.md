---
title: Запуск программ Linux в Windows
ms.date: 07/31/2019
helpviewer_keywords:
- Linux [C++], porting to Win32
ms.assetid: 3837e4fe-3f96-4f24-b2a1-7be94718a881
ms.openlocfilehash: c91bcf1c9384cd71811d42a14b98dc155626a4d5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368470"
---
# <a name="running-linux-programs-on-windows"></a>Запуск программ Linux в Windows

Для запуска программы Linux в Windows возможны следующие варианты:

- Запуск программы "как есть" в подсистеме Windows для Linux (WSL). В WSL программа выполняется непосредственно на оборудовании компьютера, а не на виртуальной машине. WSL также поддерживает прямые вызовы файловой системы между системами Windows и Linux, устраняя необходимость в SSL-транспорте. WSL разработана как среда командной строки и не рекомендуется для приложений, интенсивно использующих графику. Дополнительные сведения см. в [документации по подсистеме Windows для Linux](/windows/wsl/about).
- Запуск программы "как есть" на виртуальной машине Linux или в контейнере Docker на локальном компьютере или в Azure. Дополнительные сведения см. в разделах [Виртуальные машины](https://azure.microsoft.com/services/virtual-machines/) и [Docker в Azure](https://docs.microsoft.com/azure/docker/).
- Компиляция программы с использованием gcc или clang в средах [MinGW](http://MinGW.org/) или [MinGW-w64](https://sourceforge.net/p/mingw-w64/wiki2/Home/), которые предоставляют слой преобразования системных вызовов Linux в системные вызовы Windows.
- Компиляция и запуск программы с использованием gcc или clang в среде [Cygwin](https://www.cygwin.com/), которая предоставляет более полную среду Linux в Windows по сравнению с MinGW или MinGW-w64.
- Ручное портирование кода из Linux и компиляция для Windows с использованием Microsoft C++ (MSVC). Этот подход подразумевает рефакторинг кода, не зависящего от платформы, в отдельные библиотеки, и последующее переписывание специализированного кода, относящегося к Linux, в код для Windows (например, для API-интерфейсов Win32 или DirectX). Предположительно, этот вариант лучше всего подходит для приложений, в которых требуется высокопроизводительная графика.
