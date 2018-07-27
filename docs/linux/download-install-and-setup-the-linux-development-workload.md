---
title: Установка рабочей нагрузки Linux для проектов C++ в Visual Studio | Документация Майкрософт
description: Скачивание, установка и настройка рабочей нагрузки Linux для проектов C++ в Visual Studio.
ms.custom: ''
ms.date: 07/20/2018
ms.technology:
- cpp-linux
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: e33b9ac72ca7691ccbb80a9a30349d3a1e31e194
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207563"
---
# <a name="download-install-and-setup-the-linux-workload"></a>Загрузка, установка и настройка рабочей нагрузки Linux

Чтобы использовать Visual Studio IDE для создания и отладки проектов C++ в Linux, нужно установить рабочую нагрузку **разработки на C++ для Linux**.

## <a name="visual-studio-setup"></a>Установка Visual Studio
1. Запустите установщик Visual Studio и выберите рабочую нагрузку **Разработка приложений Linux на C++**.

   ![Расширение "Visual C++ для разработки в среде Linux"](media/linuxworkload.png)

2. Для продолжения установки нажмите кнопку **Установить**.

## <a name="linux-setup"></a>Установка Linux
На целевом компьютере Linux должны быть установлены **openssh-server**, **g++**, **gdb** и **gdbserver** и запущена управляющая программа SSH.  Если они еще не установлены, их можно установить следующим образом.
 
1. В командной строке оболочки на компьютере Linux выполните следующую команду:

   `sudo apt-get install openssh-server g++ gdb gdbserver`

   Для выполнения команды sudo вам может быть предложено ввести пароль учетной записи root.  Введите его и продолжите.  После завершения эти службы и инструменты будут установлены.

1. Запустите службу ssh на компьютере Linux, выполнив следующую команду:

   `sudo service ssh start`
   
   Эта команда запустит службу в фоновом режиме для готовности к принятию подключений.
