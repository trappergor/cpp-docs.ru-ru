---
title: "Развертывание приложения Visual C++ в приложении локальную папку | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: deploying Visual C++ applications
ms.assetid: 47a81c47-9dbe-47c6-96cc-fbb2fda5e6ad
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1d9a92a5fef96932f1d6a58503fe6355b5a410ce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-deploying-a-visual-c-application-to-an-application-local-folder"></a>Пошаговое руководство. Развертывание приложения Visual C++ в локальную папку приложения
Описывает развертывание приложения Visual C++ путем копирования файлов в его папку.  
  
## <a name="prerequisites"></a>Предварительные требования  
  
-   Компьютер с установленной среды Visual Studio.  
  
-   Другой компьютер, который не установлены библиотеки Visual C++.  
  
### <a name="to-deploy-an-application-to-an-application-local-folder"></a>Для развертывания приложения в локальную папку приложения  
  
1.  Создайте и постройте приложение MFC, приведенные в [Пошаговое руководство: развертывание Visual C++ приложения с помощью проекта установки](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).  
  
2.  Скопируйте соответствующие файлы библиотеки MFC и времени выполнения C (CRT) — например, для x86 платформы и поддержка Юникода, копировать файл mfc100u.dll и msvcr100.dll из Visual Studio 10.0\VC\redist\x86\—and \Program Files\Microsoft вставьте их в папке \Release\ проект MFC. Дополнительные сведения о других файлах, возможно, потребуется скопировать см. в разделе [определение библиотек DLL для распространения](../ide/determining-which-dlls-to-redistribute.md).  
  
3.  Запустите приложение MFC на втором компьютере, не установлены библиотеки Visual C++.  
  
    1.  Скопируйте содержимое папки \Release\ и вставьте их в папку приложения на втором компьютере.  
  
    2.  Запустите приложение на втором компьютере.  
  
     Приложение выполняется успешно, так как в локальную папку приложения доступны библиотеки Visual C++.  
  
## <a name="see-also"></a>См. также  
 [Примеры развертывания](../ide/deployment-examples.md)