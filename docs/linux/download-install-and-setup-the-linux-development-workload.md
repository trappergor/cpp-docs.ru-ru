---
title: "Загрузка, установка и настройка рабочей нагрузки Linux | Документы Майкрософт"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
author: BrianPeek
ms.author: brpeek
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 338f1bd87dbaaf4caf6a788cd45b3d011bbf40f0
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---

# <a name="download-install-and-setup-the-linux-workload"></a>Загрузка, установка и настройка рабочей нагрузки Linux

## <a name="visual-studio-setup"></a>Установка Visual Studio
1. Запустите установщик Visual Studio и выберите рабочую нагрузку **Разработка приложений Linux на C++**.

   ![Расширение "Visual C++ для разработки в среде Linux"](media/linuxworkload.png)

2. Для продолжения установки нажмите кнопку **Установить**.

## <a name="linux-setup"></a>Программа установки Linux
На целевом компьютере Linux должны быть установлены **openssh-server**, **g++**, **gdb** и **gdbserver** и запущена управляющая программа SSH.  Если они еще не установлены, их можно установить следующим образом.
 
1. В командной строке оболочки на компьютере Linux выполните следующую команду:

   `sudo apt-get install openssh-server g++ gdb gdbserver`

   Для выполнения команды sudo вам может быть предложено ввести пароль учетной записи root.  Введите его и продолжите.  После завершения эти службы и инструменты будут установлены.

1. Запустите службу ssh на компьютере Linux, выполнив следующую команду:

   `sudo service ssh start`
   
   Эта команда запустит службу в фоновом режиме для готовности к принятию подключений.

