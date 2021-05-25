---
description: >-
  Valve集成开发环境(Valve Integrated Development Environment
  通常简称为VIDE)是供源代码开发人员使用的第三方免费软件发行版。
---

# VIDE

Valve集成开发环境**\(Valve Integrated Development Environment** 通常简称为**VIDE\)**是供源代码开发人员使用的第三方免费软件发行版。它通常被地图制作者用来将自定义内容\([纹理](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-MaYSoe1K5NhUn60ZC2N/v/chinese/information/textures/@drafts)、[模型](https://developer.valvesoftware.com/wiki/Models)、[音景](https://developer.valvesoftware.com/wiki/Soundscapes)等\)打包到他们的关卡中。

任何和所有自定义内容必须用VIDE或者其他软件打包到关卡。否则，你的地图的其他使用者将看到[纹理丢失](https://app.gitbook.com/@noskill/s/titanfall2/~/drafts/-MaYSoe1K5NhUn60ZC2N/v/chinese/information/textures/missing-content/@drafts)的效果而不是你自定义的纹理。

## 功能

* Hammer Splitter Editor （Hammor 分配编辑器）
* Package Viewer （打包查看器 同等于 [GCFScape](https://developer.valvesoftware.com/wiki/GCFScape)\)
* Particle Editor （粒子编辑器）
* VBSP Editor （VBSP 编辑器）
* VMT Editor （VMT 编辑器）
* Mass VMT Editor（大规模VMT 编辑器）
* VTF Editor \(VTF 编辑器 同等于 [VTFEdit](../vtf-and-vmt/vtfedit.md)\)
* Mass VTF Editor （大规模VTF编辑器）
* BSP Info （BSP信息查看器）
* Entity Lump Editor \(实体块编辑器 同等于 [Entspy](entspy.md)\)
* Pakfile Lump Editor \(包文件块编辑器 同等于 [Pakrat](https://developer.valvesoftware.com/wiki/Pakrat)\)

##  更新日志（以下较为冗杂，所以暂不翻译，等有时间翻译）

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>
          <br /><b>Version 0.45b -- February 27, 2013</b>
        </p>
        <ul>
          <li><b>Pakfile Lump Editor</b>
            <ul>
              <li>Fixed: Incorrect gib model paths</li>
              <li>Fixed: Certain version 21 BSPs saved with an incorrect version identifier</li>
              <li>Fixed: Incomplete scan of pre-packed content</li>
              <li>Changed: Scanning of packed materials is now enabled by default
                <br />
              </li>
            </ul>
          </li>
          <li><b>Package Viewer</b>
            <ul>
              <li>Added: Basic VPK version 2 support</li>
            </ul>
          </li>
        </ul>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>
          <br /><b>Version 0.45a -- December 25, 2012</b>
        </p>
        <ul>
          <li><b>VIDE</b>
            <ul>
              <li>Added: VTF Editor</li>
              <li>Added: Mass VTF Editor</li>
              <li>Fixed: File dialogs now remember last directory</li>
              <li>Added: Single instance limitation</li>
              <li>Added: Open file by argument
                <br />
              </li>
            </ul>
          </li>
          <li>
            <p><b>VBSP Editor</b>
            </p>
            <ul>
              <li>Fixed: Infinite loop when setting texture dimension</li>
              <li>Fixed: Texture dimension default read from invalid prop on load</li>
              <li>Fixed: Incorrect renaming of all tree items</li>
              <li>Fixed: Swaped items are now saved in the correct order</li>
            </ul>
            <p></p>
          </li>
          <li><b>Package Viewer</b>
            <ul>
              <li>Fixed: Error when reading data from single digit VPK archive segments</li>
            </ul>
          </li>
        </ul>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>
          <br /><b>Version 0.38a -- January 9, 2012</b>
        </p>
        <ul>
          <li><b>VIDE</b>
            <ul>
              <li>Added: Package Viewer
                <br />
              </li>
            </ul>
          </li>
          <li><b>Entity Lump Editor</b>
            <ul>
              <li>Fixed: Lump written to Output window instead of BSP or LMP</li>
              <li>Fixed: Crashing when importing VMF with entity connections</li>
              <li>Fixed: Similarily named keyvalues overwriting each other</li>
              <li>Removed: Brush entities loaded/saved from/to VMF</li>
              <li>Added: Search option to invert results</li>
              <li>Added: Option to ignore importing of hidden VMF entities
                <br />
              </li>
            </ul>
          </li>
          <li><b>Hammer Splitter Editor</b>
            <ul>
              <li>Fixed: Distance fields now set value upon losing focus</li>
              <li>Fixed: Disabled editing of unreadable registry entries
                <br />
              </li>
            </ul>
          </li>
          <li><b>Mass VMT Editor</b>
            <ul>
              <li>Fixed: VTF material initialization using wrong path
                <br />
              </li>
            </ul>
          </li>
          <li><b>Pakfile Lump Editor</b>
            <ul>
              <li>Fixed: Rewrote nearly all GUI logic
                <br />
              </li>
            </ul>
          </li>
          <li><b>Particle Editor</b>
            <ul>
              <li>Fixed: Crash when context menu requested in blank space
                <br />
              </li>
            </ul>
          </li>
          <li><b>VBSP Editor</b>
            <ul>
              <li>Fixed: Various value fields setting the wrong value</li>
              <li>Added: Texture dimension default read from first prop on load
                <br />
              </li>
            </ul>
          </li>
          <li><b>[BSP Tools]</b>
            <ul>
              <li>Fixed: General inconsistancy and unreliability; rewrote BSP delegate class
                <br
                />
              </li>
            </ul>
          </li>
          <li><b>[VMF Tools]</b>
            <ul>
              <li>Changed: Rewrote VMF class
                <br />
              </li>
            </ul>
          </li>
          <li><b>[Utility Code]</b>
            <ul>
              <li>Fixed: Improved accuracy and handling of plaintext keyvalues</li>
            </ul>
          </li>
        </ul>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>
          <br /><b>Version 0.32b -- June 23, 2010</b>
        </p>
        <ul>
          <li><b>VIDE</b>
            <ul>
              <li>Removed: Public use of external log file
                <br />
              </li>
            </ul>
          </li>
          <li><b>Mass VMT Editor</b>
            <ul>
              <li>Fixed: Undesirable behaviour with empty file list
                <br />
              </li>
            </ul>
          </li>
          <li><b>Pakfile Lump Editor</b>
            <ul>
              <li>Fixed: Model materials not being searched for</li>
              <li>Added: Scan options dialog
                <br />
              </li>
            </ul>
          </li>
          <li><b>Particle Editor</b>
            <ul>
              <li>Added: System finder</li>
              <li>Added: Map particle manifester</li>
            </ul>
          </li>
        </ul>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>
          <br /><b>Version 0.32a -- June 16, 2010</b>
        </p>
        <ul>
          <li><b>VIDE</b>
            <ul>
              <li>Added: Particle Editor</li>
              <li>Added: Entity Lump Editor</li>
              <li>Added: VBSP Editor</li>
              <li>Added: Closure confirmation for modified windows</li>
              <li>Removed: Ability to move toolbars</li>
              <li>Removed: Ability to manually check for updates</li>
              <li>Removed: External program launchers
                <br />
              </li>
            </ul>
          </li>
          <li><b>BSP Info</b>
            <ul>
              <li>Added: Option to save extracted lump with lump name instead of number</li>
              <li>Added: Lump names according to BSP version
                <br />
              </li>
            </ul>
          </li>
          <li><b>Mass VMT Editor</b>
            <ul>
              <li>Added: Asterisk wildcard option</li>
              <li>Added: Improved progress dialog
                <br />
              </li>
            </ul>
          </li>
          <li><b>Pakfile Lump Editor</b>
            <ul>
              <li>Fixed: Rare crash when finishing scan for referenced content</li>
              <li>Fixed: Skybox and detail sprites not being searched for</li>
              <li>Fixed: Rare infinite loop when reading binary data as text</li>
              <li>Fixed: Editing of search path after scan</li>
              <li>Added: Ability to search for and scan particle systems
                <br />
              </li>
            </ul>
          </li>
          <li><b>VMT Editor</b>
            <ul>
              <li>Fixed: New window from opening if open dialog was canceled</li>
              <li>Added: Save shortcut &quot;Ctrl + S&quot;
                <br />
              </li>
            </ul>
          </li>
          <li><b>[BSP Tools]</b>
            <ul>
              <li>Added: Hard-coded lump names</li>
            </ul>
          </li>
        </ul>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>
          <br /><b>Version 0.16b -- February 26, 2010</b>
        </p>
        <ul>
          <li><b>VIDE</b>
            <ul>
              <li>Added: Ability to check for updates</li>
              <li>Added: About information
                <br />
              </li>
            </ul>
          </li>
          <li><b>BSP Info</b>
            <ul>
              <li>Fixed: Window opening when the file open dialog was canceled</li>
              <li>Fixed: Crash when closing a window after opening a BSP more than once</li>
              <li>Fixed: Bug preventing a BSP from being read</li>
              <li>Added: Context menu to copy lump offset and length values from the table</li>
              <li>Added: Lump manipulation: Append, Extract, Prepend, and Replace
                <br />
              </li>
            </ul>
          </li>
          <li><b>Mass VMT Editor</b>
            <ul>
              <li>Added: VMT and VTF only file type selections</li>
              <li>Added: Progress dialog for lengthy operations
                <br />
              </li>
            </ul>
          </li>
          <li><b>Pakfile Lump Editor</b>
            <ul>
              <li>Fixed: Crash when adding files with a CRC of 9F6FB22E</li>
              <li>Removed: Unnecessary status entries</li>
              <li>Added: Scan option
                <br />
              </li>
            </ul>
          </li>
          <li><b>[VMT Tools]</b>
            <ul>
              <li>Fixed: Formal syntax requirement</li>
            </ul>
          </li>
        </ul>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>
          <br /><b>Version 0.1a -- December 25, 2009</b>
        </p>
        <ul>
          <li>Initial release.</li>
        </ul>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

{% hint style="info" %}
引用文献：

* [http://www.riintouge.com/VIDE/](http://www.riintouge.com/VIDE/)
* [https://developer.valvesoftware.com/wiki/VIDE](https://developer.valvesoftware.com/wiki/VIDE)
* [http://www.tophattwaffle.com/downloads/vide/](http://www.tophattwaffle.com/downloads/vide/)
{% endhint %}

