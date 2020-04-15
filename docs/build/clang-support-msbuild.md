---
title: Поддержка Clang/LLVM в проектах Visual Studio
ms.date: 08/30/2019
ms.description: Configure a Visual Studio MSBuild project to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++ MSBuild projects
ms.openlocfilehash: 8d7d7fec979d3e7b8f665e56094ee1c309e3b686
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323122"
---
# <a name="clangllvm-support-in-visual-studio-projects"></a>Поддержка Clang/LLVM в проектах Visual Studio

::: moniker range="<=vs-2017"

Clang поддержка как проектов CMake, так и MSBuild доступна в Visual Studio 2019.

::: moniker-end

::: moniker range="vs-2019"

Вы можете использовать Visual Studio 2019 версию 16.2 с Clang для отсеивательных, отвержений и отладки проектов визуальной студии C '(MSBuild), ориентированных на Windows или Linux.

## <a name="install"></a>Установка

Для лучшей поддержки IDE в Visual Studio мы рекомендуем использовать новейшие инструменты компилятора Clang для Windows. Если у вас их еще нет, вы можете установить их, открыв visual Studio Installer и выбрав **инструменты C' Clang для Windows** в **разработке рабочего стола с** дополнительными компонентами. Если вы предпочитаете использовать существующую установку Clang на вашей машине, выберите **C'Clang-cl для инструментов сборки v142.** дополнительный компонент. Стандартная библиотека Microsoft C е в настоящее время требует по крайней мере Clang 8.0.0; комплектная версия Clang будет автоматически обновляться, чтобы оставаться в курсе обновлений в реализации Стандартной библиотеки Майкрософт.

![Установка компонента ляга](media/clang-install-vs2019.png)

## <a name="configure-a-windows-project-to-use-clang-tools"></a>Настройка проекта Windows с использованием инструментов Clang

Чтобы настроить проект Visual Studio, чтобы использовать Clang, нажмите правой кнопкой мыши на узло проекта в **Solution Explorer** и выберите **Свойства.** Как правило, сначала следует выбрать **все конфигурации** в верхней части диалога. Затем, под **общим** > **инструментом платформы**, выберите **LLVM (clang-cl),** а затем **OK**.

![Установка компонента ляга](media/clang-msbuild-prop-page.png)

Если вы используете инструменты Clang, которые в комплекте с Visual Studio, никаких дополнительных шагов не требуется. Для проектов Windows Visual Studio по умолчанию ссылается на Clang в режиме [лязг-клик](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) и ссылки на реализацию Стандартной библиотеки Microsoft. По умолчанию, **clang-cl.exe** находится в `C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin`.

Если вы используете пользовательскую установку Clang, вы можете либо изменить **Project** > **Properties** > **VC ' DIrectories** > Configuration**Properties** > **Исполняемые Каталоги,** добавив `LLVMInstallDir` пользовательский корень установки Clang в качестве первого каталога, либо изменить значение свойства. Для получения дополнительной информации смотрите [специальное местоположение LLVM.](#custom_llvm_location)

## <a name="configure-a-linux-project-to-use-clang-tools"></a>Настройка linux-проекта с использованием инструментов Clang

Для linux-проектов Visual Studio использует clang GCC-совместимый фронтэнд. Свойства проекта и почти все флаги компилятора идентичны

Для настройки проекта Visual Studio Linux с использованием Clang:

1. Нажмите на узла проекта в **Solution Explorer** и выберите **свойства.**
1. Как правило, сначала следует выбрать **все конфигурации** в верхней части диалога.
1. В **рамках общей** > **платформы Toolset**выберите **WSL_Clang_1_0** если вы используете подсистему Windows для Linux, или **Remote_Clang_1_0** если вы используете удаленную машину или VM.
1. Нажмите кнопку **ОК**.

![Установка компонента ляга](media/clang-msbuild-prop-page.png)

На Linux Visual Studio по умолчанию использует первое местоположение Clang, с которым она сталкивается в свойстве среды PATH. Если вы используете пользовательскую установку Clang, то `LLVMInstallDir` вы должны изменить значение свойства или же заменить путь в **Project** > **Properties** > **VC » DIrectories** > **Конфигурация Свойства** > **Исполняемые Каталоги**. Для получения дополнительной информации смотрите [специальное местоположение LLVM.](#custom_llvm_location)

## <a name="set-a-custom-llvm-location"></a><a name="custom_llvm_location"></a>Установите пользовательское местоположение LLVM

Вы можете установить пользовательский путь для LLVM для одного или нескольких проектов, создав файл *Directory.build.props* и добавив этот файл в корневую папку любого проекта. Вы можете добавить его в папку корневого раствора, чтобы применить его ко всем проектам в решении. Файл должен выглядеть следующим образом (но заменить фактический путь):

```xml
<Project>
  <PropertyGroup>
    <LLVMInstallDir>c:\MyLLVMRootDir</LLVMInstallDir>
  </PropertyGroup>
</Project>
```

## <a name="set-additional-properties-edit-build-and-debug"></a>Установите дополнительные свойства, редотисвите, построите и отливу

После настройки конфигурации Clang нажмите еще раз на узла проекта и выберите **проект Reload.** Теперь можно создавать и отлаживать проект с помощью инструментов Clang. Visual Studio обнаруживает, что вы используете компилятор Clang, и предоставляет функции IntelliSense, выделения, навигации и других функций редактирования. Ошибки и предупреждения отображаются в **окне вывода.** Страницы свойств проекта для конфигурации Clang очень похожи на страницы MSVC, хотя некоторые объектистом-зависимые функции, такие как Edit и Continue, недоступны для конфигураций Clang. Чтобы установить компилятор Clang или опцию linker, которая недоступна на страницах свойств, вы можете добавить его вручную на страницах свойств в **соответствии** > с Configuration Properties**C/C (или Linker)** > **Командная линия** > **Дополнительные параметры.**

При отладке можно использовать точки разрыва, визуализацию памяти и данных, а также большинство других функций отладки.  

![Отладка Clang](media/clang-debug-msbuild.png)

::: moniker-end
