# Try-Catch-Finally

Try-catch wird verwendet um eventuelle Fehler eines Codeblocks abzufangen. Der Code im 
optionalen finally Block wird unabhängig von auftretenden Fehlern auf jeden Fall ausgeführt.
Meisten wird der finally Block für dispose() Zwecke verwendet.

Beispiel anhand einer Skizze:

![try-catch-finally](https://i.imgur.com/choj1Tq.png)

Konkretes Beispiel mit Code:

	public class ExampleClass
	{
		void ReadFile(int index)
		{

			string path = @"c:\users\public\test.txt";
			System.IO.StreamReader file = new System.IO.StreamReader(path);
			char[] buffer = new char[10];
			try
			{
				file.ReadBlock(buffer, index, buffer.Length);
			}
			catch (System.IO.IOException e)
			{
				Console.WriteLine("Error reading from {0}. Message = {1}", path, e.Message);
			}
        
			finally
			{
				if (file != null)
				{
					file.Close();
				}
			}
		}
	}

Weiteres Beispiel mit using:

	try
	{
		using (StreamReader sr = new StreamReader(ValidFilePathName))
		{
			line = file.ReadLine();
			While (line != null)
			{
				line = file.ReadLine();
			}
		}
	}
	catch (Exception ex)
	{
		string myException = ex.ToString();
	}

Bei dieser Methode erspart man sich den finally Block, da sich die using Methode um das dispose() kümmert.