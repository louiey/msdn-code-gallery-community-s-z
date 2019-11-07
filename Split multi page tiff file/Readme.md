# Split multi page tiff file
## Requires
- Visual Studio 2010
## License
- Apache License, Version 2.0
## Technologies
- GDI+
## Topics
- Images
- TIFF
## Updated
- 05/29/2012
## Description

<h1>Introduction</h1>
<p><em>While working with image files, one of the biggest constraint is the size of file. When file is too big, then it need too much time to process add load. So, to resolve this issue, we can split one big image (tiff) file into various pages. This code sample
 will explain how to work with TIFF (Tagged Image File Format) using c#.net. It will cover splitting&nbsp; a multipage tiff file into multiple tiff files and reading the properties of tiff file using c#. TIFF files are one of the format in whcih images can
 be saved. To split multipage tiff file, mainly 3 steps are required as 1) Get the total number of pages in a TIFF file 2) Get encoder information for the TIFF type file 3) Save each page of multipage&nbsp; TIFF file into seperate TIFF files. In TIFF, there
 are predefined types, whcih tell the value of an item is of which type</em></p>
<table class="MsoNormalTable" border="1" cellspacing="0" cellpadding="0" style="margin:auto auto auto 0.5in; border-collapse:collapse; background:#f2f2f2">
<tbody>
<tr>
<td width="80" valign="top" style="padding-bottom:0in; padding-left:5.4pt; width:59.65pt; padding-right:5.4pt; background:#dfdfdf; padding-top:0in; border:black 1pt solid">
<p class="MsoNormal" style="text-align:center; margin:0in 0in 0pt"><strong><span>Type of the Property</span></strong></p>
</td>
<td width="511" valign="top" style="border-bottom:black 1pt solid; border-left:#f0f0f0; padding-bottom:0in; padding-left:5.4pt; width:383.15pt; padding-right:5.4pt; background:#dfdfdf; border-top:black 1pt solid; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="margin:0in 0in 0pt"><strong><span>Type of Value</span></strong></p>
</td>
</tr>
<tr>
<td width="80" valign="top" style="border-bottom:black 1pt solid; border-left:black 1pt solid; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:59.65pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="text-align:center; margin:0in 0in 0pt"><span>1</span></p>
</td>
<td width="511" valign="top" style="border-bottom:black 1pt solid; border-left:#f0f0f0; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:383.15pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="margin:0in 0in 0pt"><span>Value is an array of bytes</span><span>&nbsp;</span></p>
</td>
</tr>
<tr>
<td width="80" valign="top" style="border-bottom:black 1pt solid; border-left:black 1pt solid; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:59.65pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="text-align:center; margin:0in 0in 0pt"><span>2</span></p>
</td>
<td width="511" valign="top" style="border-bottom:black 1pt solid; border-left:#f0f0f0; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:383.15pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="margin:0in 0in 0pt"><span>Value is a null-terminated ASCII string</span></p>
</td>
</tr>
<tr>
<td width="80" valign="top" style="border-bottom:black 1pt solid; border-left:black 1pt solid; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:59.65pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="text-align:center; margin:0in 0in 0pt"><span>3</span></p>
</td>
<td width="511" valign="top" style="border-bottom:black 1pt solid; border-left:#f0f0f0; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:383.15pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="margin:0in 0in 0pt"><span>Value is an array of unsigned short (16-bit) integers</span></p>
</td>
</tr>
<tr>
<td width="80" valign="top" style="border-bottom:black 1pt solid; border-left:black 1pt solid; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:59.65pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="text-align:center; margin:0in 0in 0pt"><span>4</span></p>
</td>
<td width="511" valign="top" style="border-bottom:black 1pt solid; border-left:#f0f0f0; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:383.15pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="margin:0in 0in 0pt"><span>Value is an array of unsigned long (32-bit) integers</span></p>
</td>
</tr>
<tr>
<td width="80" valign="top" style="border-bottom:black 1pt solid; border-left:black 1pt solid; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:59.65pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="text-align:center; margin:0in 0in 0pt"><span>5</span></p>
</td>
<td width="511" valign="top" style="border-bottom:black 1pt solid; border-left:#f0f0f0; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:383.15pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="margin:0in 0in 0pt"><span>Value data member is an array of pairs of unsigned long integers.</span></p>
<p class="MsoNormal" style="margin:0in 0in 0pt"><span>Each pair represents a fraction; the first integer is the numerator and the second integer is the denominator.</span></p>
</td>
</tr>
<tr>
<td width="80" valign="top" style="border-bottom:black 1pt solid; border-left:black 1pt solid; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:59.65pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="text-align:center; margin:0in 0in 0pt"><span>6</span></p>
</td>
<td width="511" valign="top" style="border-bottom:black 1pt solid; border-left:#f0f0f0; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:383.15pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="margin:0in 0in 0pt"><span>Value is an array of bytes that can hold values of any data type</span></p>
</td>
</tr>
<tr>
<td width="80" valign="top" style="border-bottom:black 1pt solid; border-left:black 1pt solid; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:59.65pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="text-align:center; margin:0in 0in 0pt"><span>7</span></p>
</td>
<td width="511" valign="top" style="border-bottom:black 1pt solid; border-left:#f0f0f0; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:383.15pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="margin:0in 0in 0pt"><span>Value is an array of signed long (32-bit) integers</span></p>
</td>
</tr>
<tr>
<td width="80" valign="top" style="border-bottom:black 1pt solid; border-left:black 1pt solid; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:59.65pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="text-align:center; margin:0in 0in 0pt"><span>10</span></p>
</td>
<td width="511" valign="top" style="border-bottom:black 1pt solid; border-left:#f0f0f0; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:383.15pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="margin:0in 0in 0pt"><span>Value is an array of pairs of signed long integers.
</span></p>
<p class="MsoNormal" style="margin:0in 0in 0pt"><span>Each pair represents a fraction; the first integer is the numerator and the second integer is the denominator.</span></p>
</td>
</tr>
</tbody>
</table>
<p>There are also some predefined IDs used for getting height, width, resolution etc for TIFF files. Below table shows some of the IDs and the associated properties:</p>
<table class="MsoNormalTable" border="1" cellspacing="0" cellpadding="0" style="margin:auto auto auto 0.5in; border-collapse:collapse; background:#f2f2f2">
<tbody>
<tr>
<td width="79" valign="top" style="padding-bottom:0in; padding-left:5.4pt; width:59.4pt; padding-right:5.4pt; background:#dfdfdf; padding-top:0in; border:black 1pt solid">
<p class="MsoNormal" style="text-align:center; margin:0in 0in 0pt"><strong><span>Id</span></strong></p>
</td>
<td width="511" valign="top" style="border-bottom:black 1pt solid; border-left:#f0f0f0; padding-bottom:0in; padding-left:5.4pt; width:383.4pt; padding-right:5.4pt; background:#dfdfdf; border-top:black 1pt solid; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="margin:0in 0in 0pt"><strong><span>Property Name</span></strong></p>
</td>
</tr>
<tr>
<td width="79" valign="top" style="border-bottom:black 1pt solid; border-left:black 1pt solid; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:59.4pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="text-align:center; margin:0in 0in 0pt"><span>256</span></p>
</td>
<td width="511" valign="top" style="border-bottom:black 1pt solid; border-left:#f0f0f0; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:383.4pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="margin:0in 0in 0pt"><span>Image Width</span></p>
</td>
</tr>
<tr>
<td width="79" valign="top" style="border-bottom:black 1pt solid; border-left:black 1pt solid; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:59.4pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="text-align:center; margin:0in 0in 0pt"><span>257</span></p>
</td>
<td width="511" valign="top" style="border-bottom:black 1pt solid; border-left:#f0f0f0; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:383.4pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="margin:0in 0in 0pt"><span>Image Length</span></p>
</td>
</tr>
<tr>
<td width="79" valign="top" style="border-bottom:black 1pt solid; border-left:black 1pt solid; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:59.4pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="text-align:center; margin:0in 0in 0pt"><span>259</span></p>
</td>
<td width="511" valign="top" style="border-bottom:black 1pt solid; border-left:#f0f0f0; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:383.4pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="margin:0in 0in 0pt"><span>Image Compression</span></p>
</td>
</tr>
<tr>
<td width="79" valign="top" style="border-bottom:black 1pt solid; border-left:black 1pt solid; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:59.4pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="text-align:center; margin:0in 0in 0pt"><span>274</span></p>
</td>
<td width="511" valign="top" style="border-bottom:black 1pt solid; border-left:#f0f0f0; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:383.4pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="margin:0in 0in 0pt"><span>Image Orientation</span></p>
</td>
</tr>
<tr>
<td width="79" valign="top" style="border-bottom:black 1pt solid; border-left:black 1pt solid; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:59.4pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="text-align:center; margin:0in 0in 0pt"><span>262</span></p>
</td>
<td width="511" valign="top" style="border-bottom:black 1pt solid; border-left:#f0f0f0; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:383.4pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="margin:0in 0in 0pt"><span>Image Photometric value</span></p>
</td>
</tr>
<tr>
<td width="79" valign="top" style="border-bottom:black 1pt solid; border-left:black 1pt solid; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:59.4pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="text-align:center; margin:0in 0in 0pt"><span>282</span></p>
</td>
<td width="511" valign="top" style="border-bottom:black 1pt solid; border-left:#f0f0f0; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:383.4pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="margin:0in 0in 0pt"><span>Image X-Resolution</span></p>
</td>
</tr>
<tr>
<td width="79" valign="top" style="border-bottom:black 1pt solid; border-left:black 1pt solid; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:59.4pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="text-align:center; margin:0in 0in 0pt"><span>283</span></p>
</td>
<td width="511" valign="top" style="border-bottom:black 1pt solid; border-left:#f0f0f0; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:383.4pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="margin:0in 0in 0pt"><span>Image Y-Resolution</span></p>
</td>
</tr>
<tr>
<td width="79" valign="top" style="border-bottom:black 1pt solid; border-left:black 1pt solid; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:59.4pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="text-align:center; margin:0in 0in 0pt"><span>269</span></p>
</td>
<td width="511" valign="top" style="border-bottom:black 1pt solid; border-left:#f0f0f0; padding-bottom:0in; background-color:transparent; padding-left:5.4pt; width:383.4pt; padding-right:5.4pt; border-top:#f0f0f0; border-right:black 1pt solid; padding-top:0in">
<p class="MsoNormal" style="margin:0in 0in 0pt"><span>Document Name</span></p>
</td>
</tr>
</tbody>
</table>
<p><span><a id="42273" href="/site/view/file/42273/1/Test%20Image.tif">Test Image.tif</a></span></p>
<h1><span>Building the Sample</span></h1>
<p><em>.&nbsp;&nbsp;&nbsp;</em>&nbsp;</p>
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>C#</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span></div>
<span class="hidden">csharp</span>
<pre class="hidden">   #region Split Tiff file

        /// &lt;summary&gt;
        /// This method is called when user clicks on the SplitTiff button
        /// &lt;/summary&gt;
        /// &lt;param name=&quot;sender&quot;&gt;&lt;/param&gt;
        /// &lt;param name=&quot;e&quot;&gt;&lt;/param&gt;
        private void btnSplitTiff_Click(object sender, EventArgs e)
        {
            try
            {
                if (!ValidateSelectedFile())
                    return;

                // Split the multipage Tiff file
                Split(txtTiffFilePath.Text, txtOutPutDir.Text);
            }
            catch
            {
                MessageBox.Show(&quot;Error occured while splitting a Tiff file.&quot;);
            }

            MessageBox.Show(@&quot;Splitted Files stored at &quot; &#43; txtOutPutDir.Text);
        }

        private void Split(string pstrInputFilePath, string pstrOutputPath)
        {
            //Get the frame dimension list from the image of the file and
            Image tiffImage = Image.FromFile(pstrInputFilePath);
            //get the globally unique identifier (GUID)
            Guid objGuid = tiffImage.FrameDimensionsList[0];
            //create the frame dimension
            FrameDimension dimension = new FrameDimension(objGuid);
            //Gets the total number of frames in the .tiff file
            int noOfPages = tiffImage.GetFrameCount(dimension);

            ImageCodecInfo encodeInfo = null;
            ImageCodecInfo[] imageEncoders = ImageCodecInfo.GetImageEncoders();
            for (int j = 0; j &lt; imageEncoders.Length; j&#43;&#43;)
            {
                if (imageEncoders[j].MimeType == &quot;image/tiff&quot;)
                {
                    encodeInfo = imageEncoders[j];
                    break;
                }
            }

            // Save the tiff file in the output directory.
            if (!Directory.Exists(pstrOutputPath))
                Directory.CreateDirectory(pstrOutputPath);

            foreach (Guid guid in tiffImage.FrameDimensionsList)
            {
                for (int index = 0; index &lt; noOfPages; index&#43;&#43;)
                {
                    FrameDimension currentFrame = new FrameDimension(guid);
                    tiffImage.SelectActiveFrame(currentFrame, index);
                    tiffImage.Save(string.Concat(pstrOutputPath, @&quot;\&quot;, index, &quot;.TIF&quot;), encodeInfo, null);
                }
            }
        }

        /// &lt;summary&gt;
        /// This method validates the inputs
        /// &lt;/summary&gt;
        /// &lt;returns&gt;return true if the inputs are valid&lt;/returns&gt;
        private bool ValidateSelectedFile()
        {

            // Validate the file path for the selected file.
            if (txtTiffFilePath.Text.Trim().Length == 0)
            {
                MessageBox.Show(&quot;Please select Input file.&quot;);
                return false;
            }
            // Validate the output folder path
            if (txtOutPutDir.Text.Trim().Length == 0)
            {
                MessageBox.Show(&quot;Please select Output folder.&quot;);
                return false;
            }

            // Validate whether the selected file is tiff file or not
            if (!txtTiffFilePath.Text.ToLower().EndsWith(&quot;.tif&quot;) &amp;&amp; !txtTiffFilePath.Text.ToLower().EndsWith(&quot;.tiff&quot;))
            {
                MessageBox.Show(&quot;Please select Valid tiff file&quot;);
                return false;
            }

            // Validate whether file exists or not
            if (!File.Exists(txtTiffFilePath.Text))
            {
                MessageBox.Show(&quot;File doesn't exist at the specified location&quot;);
                return false;
            }

            return true;
        }

        /// &lt;summary&gt;
        /// This method will open the file dialog to select the tif file
        /// &lt;/summary&gt;
        /// &lt;param name=&quot;sender&quot;&gt;&lt;/param&gt;
        /// &lt;param name=&quot;e&quot;&gt;&lt;/param&gt;
        private void btnBrowse_Click(object sender, EventArgs e)
        {
            //Show the open dialog.
            OpenFileDialog openDialog = new OpenFileDialog();
            openDialog.Title = &quot;Select Tiff File&quot;;
            openDialog.Filter = &quot;Image Files(*.TIF)|*.TIF|Image Files(*.TIFF)|*.TIFF&quot;;
            openDialog.FilterIndex = 0;
            openDialog.RestoreDirectory = true;
            DialogResult dlgResult = new DialogResult();
            //To show the dialog box everytime ok is clicked on error keep it in while.

            dlgResult = openDialog.ShowDialog();
            switch (dlgResult)
            {
                case DialogResult.OK:
                    // Get the path for the selected file
                    txtTiffFilePath.Text = openDialog.FileName;
                    break;
                case DialogResult.Cancel:
                    break;
                default:
                    break;
            }
        }

        /// &lt;summary&gt;
        /// This method will open the folder dialog to selected the output folder
        /// &lt;/summary&gt;
        /// &lt;param name=&quot;sender&quot;&gt;&lt;/param&gt;
        /// &lt;param name=&quot;e&quot;&gt;&lt;/param&gt;
        private void btnBrowseFolder_Click(object sender, EventArgs e)
        {
            FolderBrowserDialog lobjDialog = new FolderBrowserDialog();
            lobjDialog.ShowNewFolderButton = true;
            DialogResult dlgResult = lobjDialog.ShowDialog();

            switch (dlgResult)
            {
                case DialogResult.OK:
                    // Get the path for the selected folder
                    txtOutPutDir.Text = lobjDialog.SelectedPath;
                    break;
                case DialogResult.Cancel:
                    break;
                default:
                    break;
            }
        }

        #endregion

        private void btnReadProperties_Click(object sender, EventArgs e)
        {
            if (txtTiffFilePath.Text.Trim().Length == 0)
                return;

            // Read Tiff file tags
            ReadTiffProperties(txtTiffFilePath.Text);
        }

        /// &lt;summary&gt;
        /// This method reads the value of each metadata property of the tiff file
        /// &lt;/summary&gt;
        /// &lt;param name=&quot;pstrFilePath&quot;&gt;&lt;/param&gt;
        private void ReadTiffProperties(string pstrFilePath)
        {
            try
            {
                System.Drawing.Bitmap newImage = new System.Drawing.Bitmap(pstrFilePath);

                // Get the properties collection of the file
                System.Drawing.Imaging.PropertyItem[] tiffProperties = newImage.PropertyItems;
                PropertyItem currentItem = null;
                object objValue = null;

                for (int i = 0; i &lt; tiffProperties.GetLength(0); i&#43;&#43;)
                {
                    currentItem = tiffProperties[i];                    
                    objValue = ReadPropertyValue(currentItem.Type, currentItem.Value);
                }
                newImage = null;
                tiffProperties = null;
            }
            catch (Exception ex)
            {
                MessageBox.Show(ex.ToString());
            }
        }

        /// &lt;summary&gt;
        /// This method reads the tiff property based on the property type
        /// &lt;/summary&gt;
        /// &lt;param name=&quot;pItemType&quot;&gt;&lt;/param&gt;
        /// &lt;param name=&quot;pitemValue&quot;&gt;&lt;/param&gt;
        /// &lt;returns&gt;&lt;/returns&gt;
        private object ReadPropertyValue(short pItemType, byte[] pitemValue)
        {
            // Read all the properties of the file.
            object objValue = null;
            System.Text.Encoding asciiEnc = System.Text.Encoding.ASCII;
            // Read the values based on the type of the propery
            switch (pItemType)
            {
                case 2: // Value is a null-terminated ASCII string. 
                    objValue = asciiEnc.GetString(pitemValue);
                    break;
                case 3: // Value is an array of unsigned short (16-bit) integers.
                    objValue = System.BitConverter.ToUInt16(pitemValue, 0);
                    break;
                case 4: // Value is an array of unsigned long (32-bit) integers.
                    objValue = System.BitConverter.ToUInt32(pitemValue, 0);
                    break;                
                default:
                    break;
            }
            return objValue;
        }</pre>
<div class="preview">
<pre class="csharp"><span class="cs__preproc">&nbsp;&nbsp;&nbsp;#region&nbsp;Split&nbsp;Tiff&nbsp;file</span>&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;summary&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;This&nbsp;method&nbsp;is&nbsp;called&nbsp;when&nbsp;user&nbsp;clicks&nbsp;on&nbsp;the&nbsp;SplitTiff&nbsp;button</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;/summary&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;param&nbsp;name=&quot;sender&quot;&gt;&lt;/param&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;param&nbsp;name=&quot;e&quot;&gt;&lt;/param&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">private</span>&nbsp;<span class="cs__keyword">void</span>&nbsp;btnSplitTiff_Click(<span class="cs__keyword">object</span>&nbsp;sender,&nbsp;EventArgs&nbsp;e)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">try</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">if</span>&nbsp;(!ValidateSelectedFile())&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">return</span>;&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">//&nbsp;Split&nbsp;the&nbsp;multipage&nbsp;Tiff&nbsp;file</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Split(txtTiffFilePath.Text,&nbsp;txtOutPutDir.Text);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">catch</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MessageBox.Show(<span class="cs__string">&quot;Error&nbsp;occured&nbsp;while&nbsp;splitting&nbsp;a&nbsp;Tiff&nbsp;file.&quot;</span>);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MessageBox.Show(@<span class="cs__string">&quot;Splitted&nbsp;Files&nbsp;stored&nbsp;at&nbsp;&quot;</span>&nbsp;&#43;&nbsp;txtOutPutDir.Text);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">private</span>&nbsp;<span class="cs__keyword">void</span>&nbsp;Split(<span class="cs__keyword">string</span>&nbsp;pstrInputFilePath,&nbsp;<span class="cs__keyword">string</span>&nbsp;pstrOutputPath)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">//Get&nbsp;the&nbsp;frame&nbsp;dimension&nbsp;list&nbsp;from&nbsp;the&nbsp;image&nbsp;of&nbsp;the&nbsp;file&nbsp;and</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Image&nbsp;tiffImage&nbsp;=&nbsp;Image.FromFile(pstrInputFilePath);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">//get&nbsp;the&nbsp;globally&nbsp;unique&nbsp;identifier&nbsp;(GUID)</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Guid&nbsp;objGuid&nbsp;=&nbsp;tiffImage.FrameDimensionsList[<span class="cs__number">0</span>];&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">//create&nbsp;the&nbsp;frame&nbsp;dimension</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;FrameDimension&nbsp;dimension&nbsp;=&nbsp;<span class="cs__keyword">new</span>&nbsp;FrameDimension(objGuid);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">//Gets&nbsp;the&nbsp;total&nbsp;number&nbsp;of&nbsp;frames&nbsp;in&nbsp;the&nbsp;.tiff&nbsp;file</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">int</span>&nbsp;noOfPages&nbsp;=&nbsp;tiffImage.GetFrameCount(dimension);&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ImageCodecInfo&nbsp;encodeInfo&nbsp;=&nbsp;<span class="cs__keyword">null</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ImageCodecInfo[]&nbsp;imageEncoders&nbsp;=&nbsp;ImageCodecInfo.GetImageEncoders();&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">for</span>&nbsp;(<span class="cs__keyword">int</span>&nbsp;j&nbsp;=&nbsp;<span class="cs__number">0</span>;&nbsp;j&nbsp;&lt;&nbsp;imageEncoders.Length;&nbsp;j&#43;&#43;)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">if</span>&nbsp;(imageEncoders[j].MimeType&nbsp;==&nbsp;<span class="cs__string">&quot;image/tiff&quot;</span>)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;encodeInfo&nbsp;=&nbsp;imageEncoders[j];&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">break</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">//&nbsp;Save&nbsp;the&nbsp;tiff&nbsp;file&nbsp;in&nbsp;the&nbsp;output&nbsp;directory.</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">if</span>&nbsp;(!Directory.Exists(pstrOutputPath))&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Directory.CreateDirectory(pstrOutputPath);&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">foreach</span>&nbsp;(Guid&nbsp;guid&nbsp;<span class="cs__keyword">in</span>&nbsp;tiffImage.FrameDimensionsList)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">for</span>&nbsp;(<span class="cs__keyword">int</span>&nbsp;index&nbsp;=&nbsp;<span class="cs__number">0</span>;&nbsp;index&nbsp;&lt;&nbsp;noOfPages;&nbsp;index&#43;&#43;)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;FrameDimension&nbsp;currentFrame&nbsp;=&nbsp;<span class="cs__keyword">new</span>&nbsp;FrameDimension(guid);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;tiffImage.SelectActiveFrame(currentFrame,&nbsp;index);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;tiffImage.Save(<span class="cs__keyword">string</span>.Concat(pstrOutputPath,&nbsp;@<span class="cs__string">&quot;\&quot;,&nbsp;index,&nbsp;&quot;</span>.TIF&quot;),&nbsp;encodeInfo,&nbsp;<span class="cs__keyword">null</span>);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;summary&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;This&nbsp;method&nbsp;validates&nbsp;the&nbsp;inputs</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;/summary&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;returns&gt;return&nbsp;true&nbsp;if&nbsp;the&nbsp;inputs&nbsp;are&nbsp;valid&lt;/returns&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">private</span>&nbsp;<span class="cs__keyword">bool</span>&nbsp;ValidateSelectedFile()&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">//&nbsp;Validate&nbsp;the&nbsp;file&nbsp;path&nbsp;for&nbsp;the&nbsp;selected&nbsp;file.</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">if</span>&nbsp;(txtTiffFilePath.Text.Trim().Length&nbsp;==&nbsp;<span class="cs__number">0</span>)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MessageBox.Show(<span class="cs__string">&quot;Please&nbsp;select&nbsp;Input&nbsp;file.&quot;</span>);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">return</span>&nbsp;<span class="cs__keyword">false</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">//&nbsp;Validate&nbsp;the&nbsp;output&nbsp;folder&nbsp;path</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">if</span>&nbsp;(txtOutPutDir.Text.Trim().Length&nbsp;==&nbsp;<span class="cs__number">0</span>)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MessageBox.Show(<span class="cs__string">&quot;Please&nbsp;select&nbsp;Output&nbsp;folder.&quot;</span>);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">return</span>&nbsp;<span class="cs__keyword">false</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">//&nbsp;Validate&nbsp;whether&nbsp;the&nbsp;selected&nbsp;file&nbsp;is&nbsp;tiff&nbsp;file&nbsp;or&nbsp;not</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">if</span>&nbsp;(!txtTiffFilePath.Text.ToLower().EndsWith(<span class="cs__string">&quot;.tif&quot;</span>)&nbsp;&amp;&amp;&nbsp;!txtTiffFilePath.Text.ToLower().EndsWith(<span class="cs__string">&quot;.tiff&quot;</span>))&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MessageBox.Show(<span class="cs__string">&quot;Please&nbsp;select&nbsp;Valid&nbsp;tiff&nbsp;file&quot;</span>);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">return</span>&nbsp;<span class="cs__keyword">false</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">//&nbsp;Validate&nbsp;whether&nbsp;file&nbsp;exists&nbsp;or&nbsp;not</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">if</span>&nbsp;(!File.Exists(txtTiffFilePath.Text))&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MessageBox.Show(<span class="cs__string">&quot;File&nbsp;doesn't&nbsp;exist&nbsp;at&nbsp;the&nbsp;specified&nbsp;location&quot;</span>);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">return</span>&nbsp;<span class="cs__keyword">false</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">return</span>&nbsp;<span class="cs__keyword">true</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;summary&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;This&nbsp;method&nbsp;will&nbsp;open&nbsp;the&nbsp;file&nbsp;dialog&nbsp;to&nbsp;select&nbsp;the&nbsp;tif&nbsp;file</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;/summary&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;param&nbsp;name=&quot;sender&quot;&gt;&lt;/param&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;param&nbsp;name=&quot;e&quot;&gt;&lt;/param&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">private</span>&nbsp;<span class="cs__keyword">void</span>&nbsp;btnBrowse_Click(<span class="cs__keyword">object</span>&nbsp;sender,&nbsp;EventArgs&nbsp;e)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">//Show&nbsp;the&nbsp;open&nbsp;dialog.</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;OpenFileDialog&nbsp;openDialog&nbsp;=&nbsp;<span class="cs__keyword">new</span>&nbsp;OpenFileDialog();&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;openDialog.Title&nbsp;=&nbsp;<span class="cs__string">&quot;Select&nbsp;Tiff&nbsp;File&quot;</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;openDialog.Filter&nbsp;=&nbsp;<span class="cs__string">&quot;Image&nbsp;Files(*.TIF)|*.TIF|Image&nbsp;Files(*.TIFF)|*.TIFF&quot;</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;openDialog.FilterIndex&nbsp;=&nbsp;<span class="cs__number">0</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;openDialog.RestoreDirectory&nbsp;=&nbsp;<span class="cs__keyword">true</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DialogResult&nbsp;dlgResult&nbsp;=&nbsp;<span class="cs__keyword">new</span>&nbsp;DialogResult();&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">//To&nbsp;show&nbsp;the&nbsp;dialog&nbsp;box&nbsp;everytime&nbsp;ok&nbsp;is&nbsp;clicked&nbsp;on&nbsp;error&nbsp;keep&nbsp;it&nbsp;in&nbsp;while.</span>&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dlgResult&nbsp;=&nbsp;openDialog.ShowDialog();&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">switch</span>&nbsp;(dlgResult)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">case</span>&nbsp;DialogResult.OK:&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">//&nbsp;Get&nbsp;the&nbsp;path&nbsp;for&nbsp;the&nbsp;selected&nbsp;file</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;txtTiffFilePath.Text&nbsp;=&nbsp;openDialog.FileName;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">break</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">case</span>&nbsp;DialogResult.Cancel:&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">break</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">default</span>:&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">break</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;summary&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;This&nbsp;method&nbsp;will&nbsp;open&nbsp;the&nbsp;folder&nbsp;dialog&nbsp;to&nbsp;selected&nbsp;the&nbsp;output&nbsp;folder</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;/summary&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;param&nbsp;name=&quot;sender&quot;&gt;&lt;/param&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;param&nbsp;name=&quot;e&quot;&gt;&lt;/param&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">private</span>&nbsp;<span class="cs__keyword">void</span>&nbsp;btnBrowseFolder_Click(<span class="cs__keyword">object</span>&nbsp;sender,&nbsp;EventArgs&nbsp;e)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;FolderBrowserDialog&nbsp;lobjDialog&nbsp;=&nbsp;<span class="cs__keyword">new</span>&nbsp;FolderBrowserDialog();&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;lobjDialog.ShowNewFolderButton&nbsp;=&nbsp;<span class="cs__keyword">true</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DialogResult&nbsp;dlgResult&nbsp;=&nbsp;lobjDialog.ShowDialog();&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">switch</span>&nbsp;(dlgResult)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">case</span>&nbsp;DialogResult.OK:&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">//&nbsp;Get&nbsp;the&nbsp;path&nbsp;for&nbsp;the&nbsp;selected&nbsp;folder</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;txtOutPutDir.Text&nbsp;=&nbsp;lobjDialog.SelectedPath;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">break</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">case</span>&nbsp;DialogResult.Cancel:&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">break</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">default</span>:&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">break</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}<span class="cs__preproc">&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;#endregion</span>&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">private</span>&nbsp;<span class="cs__keyword">void</span>&nbsp;btnReadProperties_Click(<span class="cs__keyword">object</span>&nbsp;sender,&nbsp;EventArgs&nbsp;e)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">if</span>&nbsp;(txtTiffFilePath.Text.Trim().Length&nbsp;==&nbsp;<span class="cs__number">0</span>)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">return</span>;&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">//&nbsp;Read&nbsp;Tiff&nbsp;file&nbsp;tags</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ReadTiffProperties(txtTiffFilePath.Text);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;summary&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;This&nbsp;method&nbsp;reads&nbsp;the&nbsp;value&nbsp;of&nbsp;each&nbsp;metadata&nbsp;property&nbsp;of&nbsp;the&nbsp;tiff&nbsp;file</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;/summary&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;param&nbsp;name=&quot;pstrFilePath&quot;&gt;&lt;/param&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">private</span>&nbsp;<span class="cs__keyword">void</span>&nbsp;ReadTiffProperties(<span class="cs__keyword">string</span>&nbsp;pstrFilePath)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">try</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;System.Drawing.Bitmap&nbsp;newImage&nbsp;=&nbsp;<span class="cs__keyword">new</span>&nbsp;System.Drawing.Bitmap(pstrFilePath);&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">//&nbsp;Get&nbsp;the&nbsp;properties&nbsp;collection&nbsp;of&nbsp;the&nbsp;file</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;System.Drawing.Imaging.PropertyItem[]&nbsp;tiffProperties&nbsp;=&nbsp;newImage.PropertyItems;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;PropertyItem&nbsp;currentItem&nbsp;=&nbsp;<span class="cs__keyword">null</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">object</span>&nbsp;objValue&nbsp;=&nbsp;<span class="cs__keyword">null</span>;&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">for</span>&nbsp;(<span class="cs__keyword">int</span>&nbsp;i&nbsp;=&nbsp;<span class="cs__number">0</span>;&nbsp;i&nbsp;&lt;&nbsp;tiffProperties.GetLength(<span class="cs__number">0</span>);&nbsp;i&#43;&#43;)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;currentItem&nbsp;=&nbsp;tiffProperties[i];&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;objValue&nbsp;=&nbsp;ReadPropertyValue(currentItem.Type,&nbsp;currentItem.Value);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;newImage&nbsp;=&nbsp;<span class="cs__keyword">null</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;tiffProperties&nbsp;=&nbsp;<span class="cs__keyword">null</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">catch</span>&nbsp;(Exception&nbsp;ex)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;MessageBox.Show(ex.ToString());&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;summary&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;This&nbsp;method&nbsp;reads&nbsp;the&nbsp;tiff&nbsp;property&nbsp;based&nbsp;on&nbsp;the&nbsp;property&nbsp;type</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;/summary&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;param&nbsp;name=&quot;pItemType&quot;&gt;&lt;/param&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;param&nbsp;name=&quot;pitemValue&quot;&gt;&lt;/param&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">///&nbsp;&lt;returns&gt;&lt;/returns&gt;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">private</span>&nbsp;<span class="cs__keyword">object</span>&nbsp;ReadPropertyValue(<span class="cs__keyword">short</span>&nbsp;pItemType,&nbsp;<span class="cs__keyword">byte</span>[]&nbsp;pitemValue)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">//&nbsp;Read&nbsp;all&nbsp;the&nbsp;properties&nbsp;of&nbsp;the&nbsp;file.</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">object</span>&nbsp;objValue&nbsp;=&nbsp;<span class="cs__keyword">null</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;System.Text.Encoding&nbsp;asciiEnc&nbsp;=&nbsp;System.Text.Encoding.ASCII;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__com">//&nbsp;Read&nbsp;the&nbsp;values&nbsp;based&nbsp;on&nbsp;the&nbsp;type&nbsp;of&nbsp;the&nbsp;propery</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">switch</span>&nbsp;(pItemType)&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">case</span>&nbsp;<span class="cs__number">2</span>:&nbsp;<span class="cs__com">//&nbsp;Value&nbsp;is&nbsp;a&nbsp;null-terminated&nbsp;ASCII&nbsp;string.&nbsp;</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;objValue&nbsp;=&nbsp;asciiEnc.GetString(pitemValue);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">break</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">case</span>&nbsp;<span class="cs__number">3</span>:&nbsp;<span class="cs__com">//&nbsp;Value&nbsp;is&nbsp;an&nbsp;array&nbsp;of&nbsp;unsigned&nbsp;short&nbsp;(16-bit)&nbsp;integers.</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;objValue&nbsp;=&nbsp;System.BitConverter.ToUInt16(pitemValue,&nbsp;<span class="cs__number">0</span>);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">break</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">case</span>&nbsp;<span class="cs__number">4</span>:&nbsp;<span class="cs__com">//&nbsp;Value&nbsp;is&nbsp;an&nbsp;array&nbsp;of&nbsp;unsigned&nbsp;long&nbsp;(32-bit)&nbsp;integers.</span>&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;objValue&nbsp;=&nbsp;System.BitConverter.ToUInt32(pitemValue,&nbsp;<span class="cs__number">0</span>);&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">break</span>;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">default</span>:&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">break</span>;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs__keyword">return</span>&nbsp;objValue;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}</pre>
</div>
</div>
</div>
<h1><span>Source Code Files</span></h1>
<ul>
<li><em>source code file name #1 - summary for this source code file.</em> </li><li><em><em>source code file name #2 - summary for this source code file.</em></em>
</li></ul>
<h1>More Information</h1>
<p><em>For more information on X, see ...?</em></p>
<div class="mcePaste" id="_mcePaste" style="width:1px; height:1px; overflow:hidden; top:0px; left:-10000px">
&#65279;</div>