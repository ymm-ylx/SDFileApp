# SDFileApp
上机实践四 内部存储
Android>7.0获得外部存储设备路径建议不要使用Environment.getExternalStorageDirectory()
原因：FileNotFoundException open failed: XXXXXXX EPERM (Operation not permitted)
权限全部添加依然报错，主要因为安卓系统的权限要求非常严格
建议改成：

ContextWrapper cw = new ContextWrapper(getApplicationContext());
File directory = cw.getExternalFilesDir(Environment.DIRECTORY_MUSIC);
File file = new File(directory, "something" + ".MP3");
