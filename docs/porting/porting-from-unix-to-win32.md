---
title: Запуск программ Linux в Windows
ms.date: 07/31/2019
helpviewer_keywords:
- Linux [C++], porting to Win32
ms.assetid: 3837e4fe-3f96-4f24-b2a1-7be94718a881
ms.openlocfilehash: 1c1807cee07db479a91f45e21434b3ba13be2ab6
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076893"
---
# <a name="running-linux-programs-on-windows"></a>Запуск программ Linux в Windows

Для запуска программы Linux в Windows возможны следующие варианты:

- Запуск программы "как есть" в подсистеме Windows для Linux (WSL). В WSL программа выполняется непосредственно на оборудовании компьютера, а не на виртуальной машине. WSL также поддерживает прямые вызовы файловой системы между системами Windows и Linux, устраняя необходимость в SSL-транспорте. WSL разработана как среда командной строки и не рекомендуется для приложений, интенсивно использующих графику. Дополнительные сведения см. в [документации по подсистеме Windows для Linux](/windows/wsl/about).
- Запуск программы "как есть" на виртуальной машине Linux или в контейнере Docker на локальном компьютере или в Azure. Дополнительные сведения см. в разделах [Виртуальные машины](https://azure.microsoft.com/services/virtual-machines/) и [Docker в Azure](https://docs.microsoft.com/azure/docker/).
- Компиляция программы с использованием gcc или clang в средах [MinGW](http://MinGW.org/) или [MinGW-w64](https://MinGW-w64.org/doku.php), которые предоставляют слой преобразования системных вызовов Linux в системные вызовы Windows.
- Компиляция и запуск программы с использованием gcc или clang в среде [Cygwin](https://www.cygwin.com/), которая предоставляет более полную среду Linux в Windows по сравнению с MinGW или MinGW-w64.
- Ручное портирование кода из Linux и компиляция для Windows с использованием Microsoft C++ (MSVC). Этот подход подразумевает рефакторинг кода, не зависящего от платформы, в отдельные библиотеки, и последующее переписывание специализированного кода, относящегося к Linux, в код для Windows (например, для API-интерфейсов Win32 или DirectX). Предположительно, этот вариант лучше всего подходит для приложений, в которых требуется высокопроизводительная графика.
