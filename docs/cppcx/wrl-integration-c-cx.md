---
title: "Интеграция с WRL (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3ad43894-c574-477c-ad3e-240301f381d4
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Интеграция с WRL (C++/CX)
Можно свободно возможность сочетать код [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] с кодом [!INCLUDE[cppwrl](../cppcx/includes/cppwrl-md.md)] \([!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)]\). В одной и той же записи преобразования можно использовать объекты, объявленные с помощью нотации дескриптора объекта [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] \(`^`\) и с помощью нотации интеллектуального указателя [!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)] \(`ComPtr<T>`\). Однако необходимо вручную обрабатывать возвращаемые значения, а также коды ошибок [!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)] HRESULT и исключения [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)].  
  
## Разработка [!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)]  
 Дополнительные сведения о разработке и использовании компонентов [!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)] см. в разделе [Библиотека шаблонов C\+\+ среды выполнения Windows \(WRL\)](http://msdn.microsoft.com/library/b915afce-553b-44a7-b8dc-0ab601758eb0).  
  
## Пример  
 Следующий фрагмент кода демонстрирует использование [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] и [!INCLUDE[cppwrl_short](../cppcx/includes/cppwrl-short-md.md)] для использования классов [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] и анализа файла метаданных.  
  
 Этот пример взят из фрагмента кода, опубликованного на [форуме по разработке приложений для Магазина Windows](http://social.msdn.microsoft.com/Forums/winappswithnativecode/thread/211ef583-db11-4e55-926b-6d9ab53dbdb4). Автор этого фрагмента кода приводит следующие замечания и оговорки:  
  
1.  C\+\+ не предоставляет конкретные API для отражения типов [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], но файлы метаданных Windows \(с расширением WINMD\) для типа полностью совместимы с файлами метаданных среды CLR. Windows предоставляет новые API обнаружения метаданных \(RoGetMetaDataFile\), позволяющие получить WINMD\-файл для указанного типа. Однако возможности применения этих API при разработке в C\+\+ ограничены, поскольку пользователь не может создать экземпляр класса.  
  
2.  После компиляции кода необходимо передать файлы Runtimeobject.lib и Rometadata.lib компоновщику.  
  
3.  Этот фрагмент предоставляется на условиях "как есть". В принципе он должен работать правильно, однако возможность ошибок не исключена.  
  
```  
  
#include <hstring.h> #include <cor.h> #include <rometadata.h> #include <rometadataresolution.h> #include <collection.h> namespace ABI_Isolation_Workaround { #include <inspectable.h> #include <WeakReference.h> } using namespace ABI_Isolation_Workaround; #include <wrl/client.h> using namespace Microsoft::WRL; using namespace Windows::Foundation::Collections; IVector<String^>^ GetTypeMethods(Object^); MainPage::MainPage() { InitializeComponent(); Windows::Foundation::Uri^ uri = ref new Windows::Foundation::Uri("http://buildwindows.com/"); auto methods = GetTypeMethods(uri); std::wstring strMethods; std::for_each(begin(methods), end(methods), [&strMethods](../standard-library/string.md methodName) { strMethods += methodName->Data(); strMethods += L"\n"; }); wprintf_s(L"%s\n", strMethods.c_str()); } IVector<String^>^ GetTypeMethods(Object^ instance) { HRESULT hr; HSTRING hStringClassName; hr = instance->__cli_GetRuntimeClassName(reinterpret_cast<__cli_HSTRING__**>(&hStringClassName)); // internal method name subject to change post BUILD if (FAILED(hr)) __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD String^ className = reinterpret_cast<String^>(hStringClassName); ComPtr<IMetaDataDispenserEx> metadataDispenser;ComPtr<IMetaDataImport2> metadataImport;hr = MetaDataGetDispenser(CLSID_CorMetaDataDispenser, IID_IMetaDataDispenser, (LPVOID*)metadataDispenser.GetAddressOf()); if (FAILED(hr)) __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD HSTRING hStringFileName; mdTypeDef typeDefToken; hr = RoGetMetaDataFile(hStringClassName, metadataDispenser.Get(), &hStringFileName, &metadataImport, &typeDefToken); if (FAILED(hr)) __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD String^ fileName = reinterpret_cast<String^>(hStringFileName); HCORENUM hCorEnum = 0; mdMethodDef methodDefs[2048]; ULONG countMethodDefs = sizeof(methodDefs); hr = metadataImport->EnumMethods(&hCorEnum, typeDefToken, methodDefs, countMethodDefs,  &countMethodDefs); if (FAILED(hr)) __cli_WinRTThrowError(hr); // internal method name subject to change post BUILD wchar_t methodName[1024]; ULONG countMethodName; std::wstring strMethods; Vector<String^>^ retVal = ref new Vector<String^>(); for(int i = 0; i < countMethodDefs; ++i) { countMethodName = sizeof(methodName); hr = metadataImport->GetMethodProps(methodDefs[i], nullptr, methodName, countMethodName, &countMethodName, nullptr, nullptr, nullptr, nullptr, nullptr); if (SUCCEEDED(hr)) { methodName[ countMethodName ] = 0; retVal->Append(ref new String(methodName)); } } return retVal; }  
  
```  
  
## См. также  
 [Взаимодействие с другими языками](../cppcx/interoperating-with-other-languages-c-cx.md)