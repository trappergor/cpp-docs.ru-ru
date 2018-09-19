---
title: Тестирование поставщика | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, testing
ms.assetid: bf824fe4-81af-4ffb-beb3-4fa2928dc450
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d175216fedb2e6a9139d970fc7696672576f7423
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042901"
---
# <a name="testing-your-provider"></a>Тестирование поставщика

Перед выпуском поставщика, следует выполнить следующие тесты, в указанном порядке. Эти тесты убедиться, что поставщик функции должным образом для большинства потенциальных пользователей.  
  
1. Проверьте его поставщик с помощью [потребителя](../../data/oledb/creating-an-ole-db-consumer.md) приложение, написанное с помощью шаблонов потребителей OLE DB. Тестовый объект-получатель должен охватывать все функциональные области поставщика (весь код, которые были добавлены или изменены).  
  
1. Проверьте его поставщик, используя приложение-потребитель, написанный с помощью ADO. Большинство разработчиков (особенно разработчиков Microsoft Visual Basic и Microsoft C#) использовать ADO или ADO.NET для клиентских приложений. Тестовый объект-получатель должен охватывать все функциональные области вашего поставщика. Пример приложения ADO потребителя, см. в разделе [примеры кода ADO в Microsoft Visual Basic](https://msdn.microsoft.com/library/ms807514.aspx).  
  
1. Запустите проверка на совместимость OLE DB (включая проверка на совместимость с ADO), чтобы убедиться, что поставщик соответствует стандарту уровня 0 для поставщиков OLE DB. (Пояснения уровня 0, выполните поиск «OLE DB уровня 0 проверка на совместимость с» в [Руководство программиста OLE DB](/previous-versions/windows/desktop/ms713643\(v=vs.85\)). Эти тесты и связанную документацию входят в состав Visual C++ в Data Access SDK. Эти тесты также помогут гарантировать, что ваш поставщик хорошо работает при сборке другими [поставщиками услуг](../../data/oledb/ole-db-resource-pooling-and-services.md) и особенно полезны при изменении или добавить свойства. Дополнительные сведения о проверка на совместимость см. в файле Readme для Data Access SDK, который находится на одном компакт-дисков Visual Studio.  
  
## <a name="see-also"></a>См. также  

[Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)