# VisualStudio2022_IllegalPathBug

![Screenshot of Error](screenshot.png?raw=true "Screenshot ")

## Crash log:
27.09.2022 17:47:29
NotRecoverable
System.ArgumentException: Illegal characters in path.
   at System.IO.Path.CheckInvalidPathChars(String path, Boolean checkAdditional)
   at System.IO.Path.GetExtension(String path)
   at Microsoft.VisualStudio.ProjectSystem.Designers.ProjectTreeIconProvider.GetIconForItem(String itemType, String itemName, String subType, Boolean expanded, Boolean exists)
   at Microsoft.VisualStudio.ProjectSystem.Designers.ProjectTreeIconProvider.CalculatePropertyValues(IProjectTreeCustomizablePropertyContext propertyContext, IProjectTreeCustomizablePropertyValues propertyValues)
   at Microsoft.VisualStudio.ProjectSystem.Designers.PhysicalProjectTreeProvider.ApplyPropertiesProviderExtensions(ProjectTreeCustomizablePropertyContext& context, IProjectTreeCustomizablePropertyValues values)
   at Microsoft.VisualStudio.ProjectSystem.Designers.PhysicalProjectTreeProvider.ConstructProjectTree(PendingProjectTreeItem pendingItem, ConfiguredProjectExports configuredProjectExports, ProjectTreeFlags parentFlags, Int32& itemsCreatedCount)
   at Microsoft.VisualStudio.ProjectSystem.Designers.PhysicalProjectTreeProvider.ConstructProjectTree(PendingFolder folder, String fullPath, String projectRelativePath, ConfiguredProjectExports configuredProjectExports, ProjectTreeFlags parentFlags, CancellationToken cancellationToken)
   at Microsoft.VisualStudio.ProjectSystem.Designers.PhysicalProjectTreeProvider.ConstructProjectTree(PendingFolder folder, String fullPath, String projectRelativePath, ConfiguredProjectExports configuredProjectExports, ProjectTreeFlags parentFlags, CancellationToken cancellationToken)
   at Microsoft.VisualStudio.ProjectSystem.Designers.PhysicalProjectTreeProvider.GenerateOriginalTree(ConfiguredProjectExports configuredProjectExports, CancellationToken cancellationToken)
   at Microsoft.VisualStudio.ProjectSystem.Designers.PhysicalProjectTreeProvider.<GenerateOriginalTreeAsync>d__235.MoveNext()
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at Microsoft.VisualStudio.ProjectSystem.ProjectTreeProviderBase.TreeUpdateSubmission.<UpdateTree>d__19.MoveNext()
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at Microsoft.VisualStudio.ProjectSystem.CoreProjectTreeProviderBase.<>c__DisplayClass76_1.<<Initialize>b__2>d.MoveNext()
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at Microsoft.VisualStudio.ProjectSystem.CoreProjectTreeProviderBase.<>c__DisplayClass78_0.<<SubmitTreeUpdateCoreAsync>g__WaitOnTask|0>d.MoveNext()
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at Microsoft.VisualStudio.ProjectSystem.CommonProjectSystemTools.Rethrow(Exception ex)
   at Microsoft.VisualStudio.ProjectSystem.ExceptionFilter.<>c__DisplayClass2_0.<Guard>g__Action|0()
   at GuardMethodClass.GuardMethod(Func`1 , Func`2 , Func`2 )
RunningInVisualStudio Microsoft.VisualStudio.ProjectSystem.RetailRuntime HostSetActiveProjectConfiguration

27.09.2022 17:47:30
Recoverable
System.AggregateException: One or more errors occurred. ---> System.ArgumentException: Illegal characters in path.
   at Microsoft.VisualStudio.ProjectSystem.VS.Implementation.Package.ProjectFactory.Prefetcher.<LoadProjectAsync>d__39.MoveNext()
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at Microsoft.VisualStudio.Threading.JoinableTask.CompleteOnCurrentThread()
   at Microsoft.VisualStudio.Threading.JoinableTask`1.CompleteOnCurrentThread()
   at Microsoft.VisualStudio.ProjectSystem.VS.Implementation.Package.ProjectFactory.CreateProject(String fileName, String location, String name, UInt32 flags, Guid& projectIid, IntPtr& project, Int32& canceled)
   at Microsoft.VisualStudio.Shell.Flavor.FlavoredProjectFactoryBase.Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject(String fileName, String location, String name, UInt32 flags, Guid& projectGuid, IntPtr& project, Int32& canceled)
   --- End of inner exception stack trace ---
---> (Inner Exception #0) System.ArgumentException: Illegal characters in path.
   at Microsoft.VisualStudio.ProjectSystem.VS.Implementation.Package.ProjectFactory.Prefetcher.<LoadProjectAsync>d__39.MoveNext()
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at Microsoft.VisualStudio.Threading.JoinableTask.CompleteOnCurrentThread()
   at Microsoft.VisualStudio.Threading.JoinableTask`1.CompleteOnCurrentThread()
   at Microsoft.VisualStudio.ProjectSystem.VS.Implementation.Package.ProjectFactory.CreateProject(String fileName, String location, String name, UInt32 flags, Guid& projectIid, IntPtr& project, Int32& canceled)
   at Microsoft.VisualStudio.Shell.Flavor.FlavoredProjectFactoryBase.Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject(String fileName, String location, String name, UInt32 flags, Guid& projectGuid, IntPtr& project, Int32& canceled)<---