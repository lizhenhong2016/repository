```
public static void BrowserFile(this HttpContext httpContext, byte[] buffer, string fileName)
{
fileName = httpContext.Request.GetFileName(fileName);
fileName = ToHexString(fileName);

string strFileName = String.Format("attachment;FileName=\"{0}\"", fileName);

httpContext.Response.ClearHeaders();
httpContext.Response.Clear();
httpContext.Response.Buffer = false;
httpContext.Response.Charset = "utf-8";
httpContext.Response.ContentType = "application/octet-stream";
httpContext.Response.AppendHeader("content-disposition", strFileName);
httpContext.Response.AddHeader("Content-Length", buffer.Length.ToString());
httpContext.Response.OutputStream.Write(buffer, 0, buffer.Length);
httpContext.Response.Flush();
httpContext.Response.End();
}
```



