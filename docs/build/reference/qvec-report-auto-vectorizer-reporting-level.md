---
title: -Qvec-report (уровень отчетности автоматического Векторизатора) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 4778c9a3-0692-4085-9b05-1bfeadf4c74a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 85f9d1c63f41b28982018bbe4507ff6bf87158fb
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43685857"
---
# <a name="qvec-report-auto-vectorizer-reporting-level"></a>/Qvec-report (уровень отчетности автоматического векторизатора)
Включает функцию отчетов компилятора [— Диагностика автоматического Векторизатора](../../parallel/auto-parallelization-and-auto-vectorization.md) и указывает уровень информационных сообщений для выходных данных во время компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Qvec-report:{1}{2}  
```  
  
## <a name="remarks"></a>Примечания  
 **/ Qvec-report: 1**  
 Выводит информационное сообщение для циклов, которые будут преобразованы в векторный формат.  
  
 **/ Qvec-report: 2**  
 Выводит информационное сообщение для циклов, которые будут преобразованы в векторный формат, а также для циклов, которые являются не преобразованы в векторный формат, с указанием кода причины.  
  
 Сведения о кодах причин и сообщениях см. в разделе [сообщения Векторизатора и Параллелизатора](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
### <a name="to-set-the-qvec-report-compiler-option-in-visual-studio"></a>Установка параметра компилятора /Qvec-report в Visual Studio  
  
1.  В области **Обозреватель решений**откройте контекстное меню для проекта и выберите пункт **Свойства**.  
  
2.  В **страницы свойств** диалогового **C/C++** выберите **командной строки**.  
  
3.  В **Дополнительные параметры** введите `/Qvec-report:1` или `/Qvec-report:2`.  
  
### <a name="to-set-the-qvec-report-compiler-option-programmatically"></a>Установка параметра компилятора /Qvec-report программным способом  
  
-   Используйте пример кода в <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры /Q (низкоуровневые операции)](../../build/reference/q-options-low-level-operations.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [Параллельное программирование в машинном коде](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/04/12/auto-vectorizer-in-visual-studio-2012-overview/)