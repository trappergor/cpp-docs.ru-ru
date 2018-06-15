---
title: Развертывание приложения Visual C++ в локальную папку приложения | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying Visual C++ applications
ms.assetid: 47a81c47-9dbe-47c6-96cc-fbb2fda5e6ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a02e585dc2b82c8b8ad675907e4205db6ad7279
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "33337913"
---
# <a name="walkthrough-deploying-a-visual-c-application-to-an-application-local-folder"></a>Пошаговое руководство. Развертывание приложения Visual C++ в локальную папку приложения
Описывает развертывания приложения Visual C++ путем копирования файлов в его папку.  
  
## <a name="prerequisites"></a>Предварительные требования  
  
-   Компьютер, где установлена среда Visual Studio.  
  
-   Другой компьютер, где не установлены библиотеки Visual C++.  
  
### <a name="to-deploy-an-application-to-an-application-local-folder"></a>Развертывание приложения в локальную папку приложения  
  
1.  Вы можете создать приложение MFC и выполнить его сборку, выполнив инструкции в разделе [Пошаговое руководство. Развертывание приложения Visual C++ с помощью проекта установки](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).  
  
2.  Скопируйте соответствующие файлы библиотеки MFC и среды выполнения C (CRT), например, для платформы x86 и поддержки Юникода скопируйте mfc100u.dll и msvcr100.dll из \Program Files\Microsoft Visual Studio 10.0\VC\redist\x86\, а затем вставьте их в папку \Release\ своего проекта MFC. Дополнительные сведения о других файлах, которые может потребоваться скопировать, см. в разделе [Определение библиотек DLL для распространения](../ide/determining-which-dlls-to-redistribute.md).  
  
3.  Запустите приложение MFC на втором компьютере, где не установлены библиотеки Visual C++.  
  
    1.  Скопируйте содержимое папки \Release\ и вставьте его в папку приложения на втором компьютере.  
  
    2.  Запустите приложение на втором компьютере.  
  
     Приложение выполняется успешно, так как в локальной папке приложения доступны библиотеки Visual C++.  
  
## <a name="see-also"></a>См. также  
 [Примеры развертывания](../ide/deployment-examples.md)