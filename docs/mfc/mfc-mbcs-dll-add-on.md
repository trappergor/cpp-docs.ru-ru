---
title: Надстройка DLL MBCS MFC
ms.date: 12/02/2019
helpviewer_keywords:
- MBCS
- MFC
ms.openlocfilehash: 522bd5cf573aa3a0b24f14bc50f23b0d0e300d2e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625354"
---
# <a name="mfc-mbcs-dll-add-on"></a>Надстройка DLL MBCS MFC

Поддержка MFC и библиотек многобайтовых кодировок (MBCS) требует дополнительного шага во время установки Visual Studio в Visual Studio 2013 и более поздних версиях.

**Visual Studio 2013**. по умолчанию библиотеки MFC, установленные в Visual Studio 2013, поддерживают только разработку с поддержкой Юникода. Для создания проекта MFC в Visual Studio 2013 необходимы DLL-файлы многобайтовых КОДИРОВОК, в которых **для свойства кодировки задано** значение **использовать многобайтовую** кодировку или **не задано**. Скачайте библиотеку DLL в [многобайтовой библиотеке MFC для Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40770).

**Visual Studio 2015**: в компоненты установки Visual C++ включены DLL-библиотеки MFC и MBCS, но поддержка MFC не устанавливается по умолчанию. Visual C++ и MFC относятся к необязательным компонентам в программе установки Visual Studio. Чтобы убедиться в том, что компонент MFC установлен, в программе установки установите переключатель **Выборочная** и в разделе **Языки программирования**убедитесь, что выбраны пункты **Visual C++** и **Microsoft Foundation Classes для C++** . Если вы уже установили Visual Studio, при попытке создания проекта MFC вам будет предложено установить Visual C++ и (или) MFC.

**Visual Studio 2017 и более поздние версии**. библиотеки DLL MFC для Юникода и MBCS устанавливаются вместе с рабочей **настольной** нагрузкой на C++ при выборе **поддержки MFC и ATL** на панели **дополнительных компонентов** в Visual Studio Installerной программе. Если установка не включает эти компоненты, перейдите к **файлу | **Диалоговое окно "Создание проектов" и щелкните ссылку **Open Visual Studio Installer (открыть** ). Дополнительные сведения см. в [статье Установка Visual Studio](/visualstudio/install/install-visual-studio).

## <a name="see-also"></a>См. также раздел

[Версии библиотек MFC](mfc-library-versions.md)
