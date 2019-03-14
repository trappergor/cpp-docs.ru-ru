---
title: Развертывание приложения Visual C++ в локальную папку
ms.date: 09/17/2018
helpviewer_keywords:
- deploying Visual C++ applications
ms.assetid: 47a81c47-9dbe-47c6-96cc-fbb2fda5e6ad
ms.openlocfilehash: 33edf4bb736fad62928e11dd0550af6640d411ac
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57746764"
---
# <a name="walkthrough-deploying-a-visual-c-application-to-an-application-local-folder"></a>Пошаговое руководство. Развертывание приложения Visual C++ в локальную папку приложения

Описывает развертывания приложения Visual C++ путем копирования файлов в его папку.

## <a name="prerequisites"></a>Предварительные требования

- Компьютер, где установлена среда Visual Studio.

- Другой компьютер, где не установлены библиотеки Visual C++.

### <a name="to-deploy-an-application-to-an-application-local-folder"></a>Развертывание приложения в локальную папку приложения

1. Вы можете создать приложение MFC и выполнить его сборку, следуя инструкциям в разделе [Пошаговое руководство. Развертывание приложения Visual C++ с помощью проекта установки](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).

1. Скопируйте соответствующие файлы библиотеки MFC и среды выполнения C (CRT) из каталога установки Visual Studio в \\VC\\redist\\*version*, а затем вставьте их в папку \Release\ своего проекта MFC. Дополнительные сведения о других файлах, которые может потребоваться скопировать, см. в разделе [Определение библиотек DLL для распространения](determining-which-dlls-to-redistribute.md).

1. Запустите приложение MFC на втором компьютере, где не установлены библиотеки Visual C++.

   1. Скопируйте содержимое папки \Release\ и вставьте его в папку приложения на втором компьютере.

   1. Запустите приложение на втором компьютере.

   Приложение выполняется успешно, так как в локальной папке приложения доступны библиотеки Visual C++.

## <a name="see-also"></a>См. также

[Примеры развертывания](deployment-examples.md)<br/>
