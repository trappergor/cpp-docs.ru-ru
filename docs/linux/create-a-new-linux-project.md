---
title: Создание проекта C++ для Linux в Visual Studio
ms.date: 06/11/2019
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
ms.openlocfilehash: 0377e21177b29d998fc3e66bb1863dbc127c1fbe
ms.sourcegitcommit: fde637f823494532314790602c2819f889706ff6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/13/2019
ms.locfileid: "67042707"
---
# <a name="create-a-new-linux-project"></a>Создание проекта Linux

::: moniker range="vs-2015"

Проекты Linux можно создавать в Visual Studio версии 2017 и выше.

::: moniker-end

Сначала убедитесь, что вы установили **рабочую нагрузку разработки для Linux** в Visual Studio. См. дополнительные сведения о [скачивании, установке и настройке рабочей нагрузки для Linux](download-install-and-setup-the-linux-development-workload.md).

При создании в Visual Studio нового проекта C++ для Linux можно выбрать его тип: Visual Studio или CMake. В этой статье описано, как создать проект Visual Studio. Сведения о создании и использовании существующих проектов CMake см. в руководстве по [созданию и настройке проектов CMake для Linux](cmake-linux-project.md).

## <a name="to-create-a-new-linux-project"></a>Создание проекта Linux

Чтобы создать проект Linux в Visual Studio, сделайте следующее:

::: moniker range="vs-2019"

1. Выберите **Файл > Создать проект** в меню Visual Studio или нажмите клавиши **Ctrl + Shift + N**.
1. Задайте для параметра **Язык** значение **C++** и выполните введите в строку поиска Linux. Выберите тип создаваемого проекта, а затем щелкните **Далее**. Укажите **имя** и **расположение**, а затем щелкните **Создать**.

   ![Новый проект Linux](media/newproject-vs2019.png)

::: moniker-end

::: moniker range="vs-2017"

1. Выберите **Файл > Создать проект** в меню Visual Studio или нажмите клавиши **Ctrl + Shift + N**.
1. Выберите узел **Visual C++ > Кроссплатформенный > Linux**, а затем укажите тип проекта, который вы хотите создать. Укажите **имя** и **расположение**, а затем щелкните **ОК**.

   ![Новый проект Linux](media/newproject.png)

::: moniker-end

   | Тип проекта | ОПИСАНИЕ |
   | ------------ | --- |
   | **Blink (Raspberry)**           | Проект для устройства Raspberry Pi с примером кода, который включает мигание светодиодного индикатора |
   | **Консольное приложение (Linux)** | Проект для любого компьютера Linux с примером кода, который выводит текст в окно консоли |
   | **Пустой проект (Linux)**       | Проект для любого компьютера Linux без примера кода |
   | **Проект Makefile (Linux)**    | Проект для любого компьютера Linux, который создается с использованием стандартной системы сборки Makefile |

   ::: moniker range="vs-2019"

   В Visual Studio 2019 можно создать новый проект CMake. Дополнительные сведения см. в статье [Настройка проекта Linux CMake](cmake-linux-project.md).
   
   ::: moniker-end

## <a name="next-steps"></a>Следующие шаги

[Настройка проекта Linux](configure-a-linux-project.md)
