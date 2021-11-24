= RAKE -- Ruby Make

home :: https://github.com/ruby/rake
bugs :: https://github.com/ruby/rake/issues
docs :: https://ruby.github.io/rake

== Description

Rake is a Make-like program implemented in Ruby. Tasks and dependencies are
specified in standard Ruby syntax.

Rake has the following features:

* Rakefiles (rake's version of Makefiles) are completely defined in
  standard Ruby syntax.  No XML files to edit.  No quirky Makefile
  syntax to worry about (is that a tab or a space?)

* Users can specify tasks with prerequisites.

* Rake supports rule patterns to synthesize implicit tasks.

* Flexible FileLists that act like arrays but know about manipulating
  file names and paths.

* A library of prepackaged tasks to make building rakefiles easier. For example,
  tasks for building tarballs. (Formerly
  tasks for building RDoc, Gems, and publishing to FTP were included in rake but they're now
  available in RDoc, RubyGems, and rake-contrib respectively.)

* Supports parallel execution of tasks.

== Installation

=== Gem Installation

Download and install rake with the following.

  gem install rake

== Usage

=== Simple Example

First, you must write a "Rakefile" file which contains the build rules. Here's
a simple example:

  task default: %w[test]

  task :test do
    ruby "test/unittest.rb"
  end

This Rakefile has two tasks:

* A task named "test", which -- upon invocation -- will run a unit test file
  in Ruby.
* A task named "default". This task does nothing by itself, but it has exactly
  one dependency, namely the "test" task. Invoking the "default" task will
  cause Rake to invoke the "test" task as well.

Running the "rake" command without any options will cause it to run the
"default" task in the Rakefile:

  % ls
  Rakefile     test/
  % rake
  (in /home/some_user/Projects/rake)
  ruby test/unittest.rb
  ....unit test output here...

Type "rake --help" for all available options.

== Resources

=== Rake Information

* {Rake command-line}[link:doc/command_line_usage.rdoc]
* {Writing Rakefiles}[link:doc/rakefile.rdoc]
* The original {Rake announcement}[link:doc/rational.rdoc]
* Rake {glossary}[link:doc/glossary.rdoc]

=== Presentations and Articles about Rake

* Avdi Grimm's rake series:
  1. {Rake Basics}[https://avdi.codes/rake-part-1-basics/]
  2. {Rake File Lists}[https://avdi.codes/rake-part-2-file-lists-2/]
  3. {Rake Rules}[https://avdi.codes/rake-part-3-rules/]
  4. {Rake Pathmap}[https://avdi.codes/rake-part-4-pathmap/]
  5. {File Operations}[https://avdi.codes/rake-part-5-file-operations/]
  6. {Clean and Clobber}[https://avdi.codes/rake-part-6-clean-and-clobber/]
  7. {MultiTask}[https://avdi.codes/rake-part-7-multitask/]
* {Jim Weirich's 2003 RubyConf presentation}[https://web.archive.org/web/20140221123354/http://onestepback.org/articles/buildingwithrake/]
* Martin Fowler's article on Rake: https://martinfowler.com/articles/rake.html

== Other Make Re-envisionings ...

Rake is a late entry in the make replacement field.  Here are links to
other projects with similar (and not so similar) goals.

* https://directory.fsf.org/wiki/Bras -- Bras, one of earliest
  implementations of "make in a scripting language".
* http://www.a-a-p.org -- Make in Python
* https://ant.apache.org -- The Ant project
* https://search.cpan.org/search?query=PerlBuildSystem -- The Perl Build System
* https://www.rubydoc.info/gems/rant/0.5.7/frames -- Rant, another Ruby make tool.

== Credits

[<b>Jim Weirich</b>] Who originally created Rake.

[<b>Ryan Dlugosz</b>] For the initial conversation that sparked Rake.

[<b>Nobuyoshi Nakada <nobu@ruby-lang.org></b>] For the initial patch for rule support.

[<b>Tilman Sauerbeck <tilman@code-monkey.de></b>] For the recursive rule patch.

[<b>Eric Hodel</b>] For aid in maintaining rake.

[<b>Hiroshi SHIBATA</b>] Maintainer of Rake 10.X and Rake 11.X

== License

Rake is available under an MIT-style license.

:include: MIT-LICENSE

---

= Other stuff

Author::   Jim Weirich <jim.weirich@gmail.com>
Requires:: Ruby 2.0.0 or later
License::  Copyright Jim Weirich.
           Released under an MIT-style license.  See the MIT-LICENSE
           file included in the distribution.

== Warranty

This software is provided "as is" and without any express or implied
warranties, including, without limitation, the implied warranties of
merchantability and fitness for a particular purpose.

== Historical

Rake was originally created by Jim Weirich, who unfortunately passed away in
February 2014. This repository was originally hosted at
{github.com/jimweirich/rake}[https://github.com/jimweirich/rake/], however
with his passing, has been moved to {ruby/rake}[https://github.com/ruby/rake].

You can view Jim's last commit here:
https://github.com/jimweirich/rake/tree/336559f28f55bce418e2ebcc0a57548dcbac4025

You can {read more about Jim}[https://en.wikipedia.org/wiki/Jim_Weirich] at Wikipedia.

Thank you for this great tool, Jim. We'll remember you.

### Contributors

<table>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/jimweirich>
            <img src=https://avatars.githubusercontent.com/u/4017?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Jim Weirich/>
            <br />
            <sub style="font-size:12px"><b>Jim Weirich</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/hsbt>
            <img src=https://avatars.githubusercontent.com/u/12301?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Hiroshi SHIBATA/>
            <br />
            <sub style="font-size:12px"><b>Hiroshi SHIBATA</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/drbrain>
            <img src=https://avatars.githubusercontent.com/u/9831?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Eric Hodel/>
            <br />
            <sub style="font-size:12px"><b>Eric Hodel</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/quix>
            <img src=https://avatars.githubusercontent.com/u/15971?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=James M. Lawrence/>
            <br />
            <sub style="font-size:12px"><b>James M. Lawrence</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/michaeljbishop>
            <img src=https://avatars.githubusercontent.com/u/1656845?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Michael Bishop/>
            <br />
            <sub style="font-size:12px"><b>Michael Bishop</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/colby-swandale>
            <img src=https://avatars.githubusercontent.com/u/996377?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Colby Swandale/>
            <br />
            <sub style="font-size:12px"><b>Colby Swandale</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/aycabta>
            <img src=https://avatars.githubusercontent.com/u/1404325?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=aycabta/>
            <br />
            <sub style="font-size:12px"><b>aycabta</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/nobu>
            <img src=https://avatars.githubusercontent.com/u/16700?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Nobuyoshi Nakada/>
            <br />
            <sub style="font-size:12px"><b>Nobuyoshi Nakada</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/randycoulman>
            <img src=https://avatars.githubusercontent.com/u/1406203?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Randy Coulman/>
            <br />
            <sub style="font-size:12px"><b>Randy Coulman</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/MehdiGol>
            <img src=https://avatars.githubusercontent.com/u/13794949?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Mehdi Golzadeh/>
            <br />
            <sub style="font-size:12px"><b>Mehdi Golzadeh</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/luislavena>
            <img src=https://avatars.githubusercontent.com/u/4182?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Luis Lavena/>
            <br />
            <sub style="font-size:12px"><b>Luis Lavena</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/eregon>
            <img src=https://avatars.githubusercontent.com/u/168854?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Benoit Daloze/>
            <br />
            <sub style="font-size:12px"><b>Benoit Daloze</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/grzuy>
            <img src=https://avatars.githubusercontent.com/u/456459?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Gonzalo/>
            <br />
            <sub style="font-size:12px"><b>Gonzalo</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/FooBarWidget>
            <img src=https://avatars.githubusercontent.com/u/819?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Hongli Lai/>
            <br />
            <sub style="font-size:12px"><b>Hongli Lai</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/pvdb>
            <img src=https://avatars.githubusercontent.com/u/17322?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Peter Vandenberk/>
            <br />
            <sub style="font-size:12px"><b>Peter Vandenberk</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/olleolleolle>
            <img src=https://avatars.githubusercontent.com/u/211?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Olle Jonsson/>
            <br />
            <sub style="font-size:12px"><b>Olle Jonsson</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/yuki24>
            <img src=https://avatars.githubusercontent.com/u/386234?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Yuki Nishijima/>
            <br />
            <sub style="font-size:12px"><b>Yuki Nishijima</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/deivid-rodriguez>
            <img src=https://avatars.githubusercontent.com/u/2887858?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=David Rodríguez/>
            <br />
            <sub style="font-size:12px"><b>David Rodríguez</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/jeremyevans>
            <img src=https://avatars.githubusercontent.com/u/3846?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Jeremy Evans/>
            <br />
            <sub style="font-size:12px"><b>Jeremy Evans</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/pskocik>
            <img src=https://avatars.githubusercontent.com/u/18250169?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=pskocik/>
            <br />
            <sub style="font-size:12px"><b>pskocik</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/satoryu>
            <img src=https://avatars.githubusercontent.com/u/124871?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Tatsuya Sato/>
            <br />
            <sub style="font-size:12px"><b>Tatsuya Sato</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/tscholz>
            <img src=https://avatars.githubusercontent.com/u/954358?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Thomas Scholz/>
            <br />
            <sub style="font-size:12px"><b>Thomas Scholz</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/raggi>
            <img src=https://avatars.githubusercontent.com/u/348?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=James Tucker/>
            <br />
            <sub style="font-size:12px"><b>James Tucker</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/keathley>
            <img src=https://avatars.githubusercontent.com/u/1642095?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Chris Keathley/>
            <br />
            <sub style="font-size:12px"><b>Chris Keathley</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/epidemian>
            <img src=https://avatars.githubusercontent.com/u/722544?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Demian Ferreiro/>
            <br />
            <sub style="font-size:12px"><b>Demian Ferreiro</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/joliss>
            <img src=https://avatars.githubusercontent.com/u/524783?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Jo Liss/>
            <br />
            <sub style="font-size:12px"><b>Jo Liss</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/JoshCheek>
            <img src=https://avatars.githubusercontent.com/u/77495?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Josh Cheek/>
            <br />
            <sub style="font-size:12px"><b>Josh Cheek</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/jasoares>
            <img src=https://avatars.githubusercontent.com/u/1004109?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=João Soares/>
            <br />
            <sub style="font-size:12px"><b>João Soares</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/xprayc>
            <img src=https://avatars.githubusercontent.com/u/514889?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Kent Wang/>
            <br />
            <sub style="font-size:12px"><b>Kent Wang</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/vipulnsward>
            <img src=https://avatars.githubusercontent.com/u/567626?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Vipul A M/>
            <br />
            <sub style="font-size:12px"><b>Vipul A M</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/ogawatti>
            <img src=https://avatars.githubusercontent.com/u/2460254?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=ogawatti/>
            <br />
            <sub style="font-size:12px"><b>ogawatti</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/amatsuda>
            <img src=https://avatars.githubusercontent.com/u/11493?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Akira Matsuda/>
            <br />
            <sub style="font-size:12px"><b>Akira Matsuda</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/snaury>
            <img src=https://avatars.githubusercontent.com/u/53117?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Alexey Borzenkov/>
            <br />
            <sub style="font-size:12px"><b>Alexey Borzenkov</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/bretts>
            <img src=https://avatars.githubusercontent.com/u/1004160?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Brett Sykes/>
            <br />
            <sub style="font-size:12px"><b>Brett Sykes</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/bhenderson>
            <img src=https://avatars.githubusercontent.com/u/26167?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Brian Henderson/>
            <br />
            <sub style="font-size:12px"><b>Brian Henderson</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/DavidEGrayson>
            <img src=https://avatars.githubusercontent.com/u/466764?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=David Grayson/>
            <br />
            <sub style="font-size:12px"><b>David Grayson</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/MarkDBlackwell>
            <img src=https://avatars.githubusercontent.com/u/692702?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Mark D. Blackwell/>
            <br />
            <sub style="font-size:12px"><b>Mark D. Blackwell</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/mjbellantoni>
            <img src=https://avatars.githubusercontent.com/u/780181?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Matthew Bellantoni/>
            <br />
            <sub style="font-size:12px"><b>Matthew Bellantoni</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/rtlechow>
            <img src=https://avatars.githubusercontent.com/u/33073?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=R.T. Lechow/>
            <br />
            <sub style="font-size:12px"><b>R.T. Lechow</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/zenspider>
            <img src=https://avatars.githubusercontent.com/u/9832?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Ryan Davis/>
            <br />
            <sub style="font-size:12px"><b>Ryan Davis</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/spastorino>
            <img src=https://avatars.githubusercontent.com/u/52642?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Santiago Pastorino/>
            <br />
            <sub style="font-size:12px"><b>Santiago Pastorino</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/seanmoon>
            <img src=https://avatars.githubusercontent.com/u/183836?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=S. S. A. Moon/>
            <br />
            <sub style="font-size:12px"><b>S. S. A. Moon</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/stuartnelson3>
            <img src=https://avatars.githubusercontent.com/u/1398104?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=stuart nelson/>
            <br />
            <sub style="font-size:12px"><b>stuart nelson</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/teoljungberg>
            <img src=https://avatars.githubusercontent.com/u/810650?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Teo Ljungberg/>
            <br />
            <sub style="font-size:12px"><b>Teo Ljungberg</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/thorsteneckel>
            <img src=https://avatars.githubusercontent.com/u/3873515?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Thorsten/>
            <br />
            <sub style="font-size:12px"><b>Thorsten</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/tmornini>
            <img src=https://avatars.githubusercontent.com/u/87?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Tom Mornini/>
            <br />
            <sub style="font-size:12px"><b>Tom Mornini</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/zzak>
            <img src=https://avatars.githubusercontent.com/u/277819?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Zachary Scott/>
            <br />
            <sub style="font-size:12px"><b>Zachary Scott</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/fhrbek>
            <img src=https://avatars.githubusercontent.com/u/562934?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Filip Hrbek/>
            <br />
            <sub style="font-size:12px"><b>Filip Hrbek</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/leethomas>
            <img src=https://avatars.githubusercontent.com/u/5622404?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Lee/>
            <br />
            <sub style="font-size:12px"><b>Lee</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/skittleys>
            <img src=https://avatars.githubusercontent.com/u/987780?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=skittleys/>
            <br />
            <sub style="font-size:12px"><b>skittleys</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/take-cheeze>
            <img src=https://avatars.githubusercontent.com/u/162074?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Takeshi Watanabe/>
            <br />
            <sub style="font-size:12px"><b>Takeshi Watanabe</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/zhustec>
            <img src=https://avatars.githubusercontent.com/u/3840198?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Zhustec/>
            <br />
            <sub style="font-size:12px"><b>Zhustec</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/bentley>
            <img src=https://avatars.githubusercontent.com/u/126009?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Anthony J. Bentley/>
            <br />
            <sub style="font-size:12px"><b>Anthony J. Bentley</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/dylanahsmith>
            <img src=https://avatars.githubusercontent.com/u/954402?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Dylan Thacker-Smith/>
            <br />
            <sub style="font-size:12px"><b>Dylan Thacker-Smith</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/jsm>
            <img src=https://avatars.githubusercontent.com/u/1446054?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Jon San Miguel/>
            <br />
            <sub style="font-size:12px"><b>Jon San Miguel</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/wwkeyboard>
            <img src=https://avatars.githubusercontent.com/u/105435?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Aaron Lee/>
            <br />
            <sub style="font-size:12px"><b>Aaron Lee</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/tenderlove>
            <img src=https://avatars.githubusercontent.com/u/3124?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Aaron Patterson/>
            <br />
            <sub style="font-size:12px"><b>Aaron Patterson</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/adamsalter>
            <img src=https://avatars.githubusercontent.com/u/786?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Adam Salter/>
            <br />
            <sub style="font-size:12px"><b>Adam Salter</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/styd>
            <img src=https://avatars.githubusercontent.com/u/8341867?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Adrian Setyadi/>
            <br />
            <sub style="font-size:12px"><b>Adrian Setyadi</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/alexch>
            <img src=https://avatars.githubusercontent.com/u/8524?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Alex Chaffee/>
            <br />
            <sub style="font-size:12px"><b>Alex Chaffee</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/cantino>
            <img src=https://avatars.githubusercontent.com/u/83835?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Andrew Cantino/>
            <br />
            <sub style="font-size:12px"><b>Andrew Cantino</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/andyg0808>
            <img src=https://avatars.githubusercontent.com/u/1283490?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Andrew Gilbert/>
            <br />
            <sub style="font-size:12px"><b>Andrew Gilbert</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/ka8725>
            <img src=https://avatars.githubusercontent.com/u/243846?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Andrei Kaleshka/>
            <br />
            <sub style="font-size:12px"><b>Andrei Kaleshka</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/alindeman>
            <img src=https://avatars.githubusercontent.com/u/395621?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Andy Lindeman/>
            <br />
            <sub style="font-size:12px"><b>Andy Lindeman</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/bjfish>
            <img src=https://avatars.githubusercontent.com/u/110023?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Brandon Fish/>
            <br />
            <sub style="font-size:12px"><b>Brandon Fish</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/e2>
            <img src=https://avatars.githubusercontent.com/u/150197?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Cezary Baginski/>
            <br />
            <sub style="font-size:12px"><b>Cezary Baginski</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/aquateen>
            <img src=https://avatars.githubusercontent.com/u/4935?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Chris Johnson/>
            <br />
            <sub style="font-size:12px"><b>Chris Johnson</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/djberg96>
            <img src=https://avatars.githubusercontent.com/u/78529?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Daniel Berger/>
            <br />
            <sub style="font-size:12px"><b>Daniel Berger</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/dancor>
            <img src=https://avatars.githubusercontent.com/u/54899?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=daniel corson/>
            <br />
            <sub style="font-size:12px"><b>daniel corson</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/danielholmes>
            <img src=https://avatars.githubusercontent.com/u/349833?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Daniel Holmes/>
            <br />
            <sub style="font-size:12px"><b>Daniel Holmes</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/danlucraft>
            <img src=https://avatars.githubusercontent.com/u/6118?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Dan Lucraft/>
            <br />
            <sub style="font-size:12px"><b>Dan Lucraft</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/dtamai>
            <img src=https://avatars.githubusercontent.com/u/1813743?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Daniel Tamai/>
            <br />
            <sub style="font-size:12px"><b>Daniel Tamai</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/pragdave>
            <img src=https://avatars.githubusercontent.com/u/10648?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Dave Thomas/>
            <br />
            <sub style="font-size:12px"><b>Dave Thomas</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/dennisjbell>
            <img src=https://avatars.githubusercontent.com/u/20423?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Dennis J. Bell/>
            <br />
            <sub style="font-size:12px"><b>Dennis J. Bell</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/DesigningPatterns>
            <img src=https://avatars.githubusercontent.com/u/14202?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Designing Patterns/>
            <br />
            <sub style="font-size:12px"><b>Designing Patterns</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/ddnexus>
            <img src=https://avatars.githubusercontent.com/u/100721?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Domizio Demichelis/>
            <br />
            <sub style="font-size:12px"><b>Domizio Demichelis</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/dslh>
            <img src=https://avatars.githubusercontent.com/u/1450065?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Doug Hammond/>
            <br />
            <sub style="font-size:12px"><b>Doug Hammond</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/esparta>
            <img src=https://avatars.githubusercontent.com/u/1037088?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Espartaco Palma/>
            <br />
            <sub style="font-size:12px"><b>Espartaco Palma</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/gfx>
            <img src=https://avatars.githubusercontent.com/u/101800?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=FUJI Goro/>
            <br />
            <sub style="font-size:12px"><b>FUJI Goro</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/felixonmars>
            <img src=https://avatars.githubusercontent.com/u/1006477?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Felix Yan/>
            <br />
            <sub style="font-size:12px"><b>Felix Yan</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/htanata>
            <img src=https://avatars.githubusercontent.com/u/21238?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Hendy Tanata/>
            <br />
            <sub style="font-size:12px"><b>Hendy Tanata</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/shirosaki>
            <img src=https://avatars.githubusercontent.com/u/170831?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Hiroshi Shirosaki/>
            <br />
            <sub style="font-size:12px"><b>Hiroshi Shirosaki</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/Elffers>
            <img src=https://avatars.githubusercontent.com/u/5466070?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=HHH/>
            <br />
            <sub style="font-size:12px"><b>HHH</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/bakunyo>
            <img src=https://avatars.githubusercontent.com/u/2487437?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=bakunyo/>
            <br />
            <sub style="font-size:12px"><b>bakunyo</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/dd1994>
            <img src=https://avatars.githubusercontent.com/u/4121510?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=JIANG Di/>
            <br />
            <sub style="font-size:12px"><b>JIANG Di</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/jswanner>
            <img src=https://avatars.githubusercontent.com/u/261?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Jacob Swanner/>
            <br />
            <sub style="font-size:12px"><b>Jacob Swanner</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/jasonkarns>
            <img src=https://avatars.githubusercontent.com/u/119972?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Jason Karns/>
            <br />
            <sub style="font-size:12px"><b>Jason Karns</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/jedcn>
            <img src=https://avatars.githubusercontent.com/u/28528?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Jed Northridge/>
            <br />
            <sub style="font-size:12px"><b>Jed Northridge</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/jessebs>
            <img src=https://avatars.githubusercontent.com/u/647843?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Jesse Bowes/>
            <br />
            <sub style="font-size:12px"><b>Jesse Bowes</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/tonytonyjan>
            <img src=https://avatars.githubusercontent.com/u/809410?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=簡煒航 (Weihang Jian)/>
            <br />
            <sub style="font-size:12px"><b>簡煒航 (Weihang Jian)</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/jrafanie>
            <img src=https://avatars.githubusercontent.com/u/19339?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Joe Rafaniello/>
            <br />
            <sub style="font-size:12px"><b>Joe Rafaniello</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/gitbisect>
            <img src=https://avatars.githubusercontent.com/u/919941?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=John Varghese/>
            <br />
            <sub style="font-size:12px"><b>John Varghese</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/jordimassaguerpla>
            <img src=https://avatars.githubusercontent.com/u/1148215?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Jordi Massaguer Pla/>
            <br />
            <sub style="font-size:12px"><b>Jordi Massaguer Pla</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/nyarly>
            <img src=https://avatars.githubusercontent.com/u/127548?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Judson Lester/>
            <br />
            <sub style="font-size:12px"><b>Judson Lester</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/astorije>
            <img src=https://avatars.githubusercontent.com/u/113730?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Jérémie Astori/>
            <br />
            <sub style="font-size:12px"><b>Jérémie Astori</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/znz>
            <img src=https://avatars.githubusercontent.com/u/11857?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Kazuhiro NISHIYAMA/>
            <br />
            <sub style="font-size:12px"><b>Kazuhiro NISHIYAMA</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/k-tsj>
            <img src=https://avatars.githubusercontent.com/u/32117?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Kazuki Tsujimoto/>
            <br />
            <sub style="font-size:12px"><b>Kazuki Tsujimoto</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/walf443>
            <img src=https://avatars.githubusercontent.com/u/2655?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Keiji, Yoshimi/>
            <br />
            <sub style="font-size:12px"><b>Keiji, Yoshimi</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/igaiga>
            <img src=https://avatars.githubusercontent.com/u/22629?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Kuniaki Igarashi/>
            <br />
            <sub style="font-size:12px"><b>Kuniaki Igarashi</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/leehambley>
            <img src=https://avatars.githubusercontent.com/u/18952?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Lee Hambley/>
            <br />
            <sub style="font-size:12px"><b>Lee Hambley</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/elgalu>
            <img src=https://avatars.githubusercontent.com/u/111569?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Leo Gallucci/>
            <br />
            <sub style="font-size:12px"><b>Leo Gallucci</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/lorensr>
            <img src=https://avatars.githubusercontent.com/u/251288?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Loren ☺️/>
            <br />
            <sub style="font-size:12px"><b>Loren ☺️</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/lzap>
            <img src=https://avatars.githubusercontent.com/u/49752?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Lukáš Zapletal/>
            <br />
            <sub style="font-size:12px"><b>Lukáš Zapletal</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/mnvr>
            <img src=https://avatars.githubusercontent.com/u/24503581?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Manav/>
            <br />
            <sub style="font-size:12px"><b>Manav</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/mpfz0r>
            <img src=https://avatars.githubusercontent.com/u/3034831?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Marco Pfatschbacher/>
            <br />
            <sub style="font-size:12px"><b>Marco Pfatschbacher</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/stomar>
            <img src=https://avatars.githubusercontent.com/u/1112299?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Marcus Stollsteimer/>
            <br />
            <sub style="font-size:12px"><b>Marcus Stollsteimer</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/mpalmer>
            <img src=https://avatars.githubusercontent.com/u/357?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Matt Palmer/>
            <br />
            <sub style="font-size:12px"><b>Matt Palmer</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/mnoble>
            <img src=https://avatars.githubusercontent.com/u/36059?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Matte Noble/>
            <br />
            <sub style="font-size:12px"><b>Matte Noble</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/kintamanimatt>
            <img src=https://avatars.githubusercontent.com/u/1854641?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Matthew Bradley/>
            <br />
            <sub style="font-size:12px"><b>Matthew Bradley</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/Elufimov>
            <img src=https://avatars.githubusercontent.com/u/423130?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Michael Elufimov/>
            <br />
            <sub style="font-size:12px"><b>Michael Elufimov</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/miry>
            <img src=https://avatars.githubusercontent.com/u/21104?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Michael Nikitochkin/>
            <br />
            <sub style="font-size:12px"><b>Michael Nikitochkin</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/mmorearty>
            <img src=https://avatars.githubusercontent.com/u/207671?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Mike Morearty/>
            <br />
            <sub style="font-size:12px"><b>Mike Morearty</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/unak>
            <img src=https://avatars.githubusercontent.com/u/17790?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=usa/>
            <br />
            <sub style="font-size:12px"><b>usa</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/noam87>
            <img src=https://avatars.githubusercontent.com/u/1909833?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Noam Gagliardi Rabinovich/>
            <br />
            <sub style="font-size:12px"><b>Noam Gagliardi Rabinovich</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/odigity>
            <img src=https://avatars.githubusercontent.com/u/155179?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Ofer Nave/>
            <br />
            <sub style="font-size:12px"><b>Ofer Nave</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/oliverklee>
            <img src=https://avatars.githubusercontent.com/u/765746?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Oliver Klee/>
            <br />
            <sub style="font-size:12px"><b>Oliver Klee</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/orien>
            <img src=https://avatars.githubusercontent.com/u/497874?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Orien Madgwick/>
            <br />
            <sub style="font-size:12px"><b>Orien Madgwick</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/pabloh>
            <img src=https://avatars.githubusercontent.com/u/134495?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Pablo Herrero/>
            <br />
            <sub style="font-size:12px"><b>Pablo Herrero</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/pda>
            <img src=https://avatars.githubusercontent.com/u/15759?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Paul Annesley/>
            <br />
            <sub style="font-size:12px"><b>Paul Annesley</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/superp>
            <img src=https://avatars.githubusercontent.com/u/86371?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Pavel Galeta/>
            <br />
            <sub style="font-size:12px"><b>Pavel Galeta</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/PChambino>
            <img src=https://avatars.githubusercontent.com/u/938444?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Pedro Chambino/>
            <br />
            <sub style="font-size:12px"><b>Pedro Chambino</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/parndt>
            <img src=https://avatars.githubusercontent.com/u/10128?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Philip Arndt/>
            <br />
            <sub style="font-size:12px"><b>Philip Arndt</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/rafaelrosafu>
            <img src=https://avatars.githubusercontent.com/u/6105?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Rafael Rosa Fu/>
            <br />
            <sub style="font-size:12px"><b>Rafael Rosa Fu</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/RDIL>
            <img src=https://avatars.githubusercontent.com/u/34555510?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Reece Dunham/>
            <br />
            <sub style="font-size:12px"><b>Reece Dunham</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/rickhull>
            <img src=https://avatars.githubusercontent.com/u/127443?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Rick Hull/>
            <br />
            <sub style="font-size:12px"><b>Rick Hull</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/robbiegill>
            <img src=https://avatars.githubusercontent.com/u/1742971?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Robbie Gill/>
            <br />
            <sub style="font-size:12px"><b>Robbie Gill</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/radar>
            <img src=https://avatars.githubusercontent.com/u/2687?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Ryan Bigg/>
            <br />
            <sub style="font-size:12px"><b>Ryan Bigg</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/ysakasin>
            <img src=https://avatars.githubusercontent.com/u/4254002?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=SAKATA Sinji/>
            <br />
            <sub style="font-size:12px"><b>SAKATA Sinji</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/salimane>
            <img src=https://avatars.githubusercontent.com/u/403938?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Salimane Adjao Moustapha/>
            <br />
            <sub style="font-size:12px"><b>Salimane Adjao Moustapha</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/sgronblo>
            <img src=https://avatars.githubusercontent.com/u/320449?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Sam Grönblom/>
            <br />
            <sub style="font-size:12px"><b>Sam Grönblom</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/plantfansam>
            <img src=https://avatars.githubusercontent.com/u/370182?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Sam/>
            <br />
            <sub style="font-size:12px"><b>Sam</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/svanderbleek>
            <img src=https://avatars.githubusercontent.com/u/491969?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Sandy Vanderbleek/>
            <br />
            <sub style="font-size:12px"><b>Sandy Vanderbleek</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/thinkerbot>
            <img src=https://avatars.githubusercontent.com/u/7307?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Simon Chiang/>
            <br />
            <sub style="font-size:12px"><b>Simon Chiang</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/urbanautomaton>
            <img src=https://avatars.githubusercontent.com/u/383376?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Simon Coffey/>
            <br />
            <sub style="font-size:12px"><b>Simon Coffey</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/sch0rsch>
            <img src=https://avatars.githubusercontent.com/u/132077?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=sch0rsch/>
            <br />
            <sub style="font-size:12px"><b>sch0rsch</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/doudou>
            <img src=https://avatars.githubusercontent.com/u/292?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Sylvain Joyeux/>
            <br />
            <sub style="font-size:12px"><b>Sylvain Joyeux</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/rctay>
            <img src=https://avatars.githubusercontent.com/u/61553?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Ray/>
            <br />
            <sub style="font-size:12px"><b>Ray</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/tmatilai>
            <img src=https://avatars.githubusercontent.com/u/79116?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Teemu Matilainen/>
            <br />
            <sub style="font-size:12px"><b>Teemu Matilainen</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/timfjord>
            <img src=https://avatars.githubusercontent.com/u/471335?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Tim Masliuchenko/>
            <br />
            <sub style="font-size:12px"><b>Tim Masliuchenko</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/TwP>
            <img src=https://avatars.githubusercontent.com/u/6323?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Tim Pease/>
            <br />
            <sub style="font-size:12px"><b>Tim Pease</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/tbrisker>
            <img src=https://avatars.githubusercontent.com/u/1540531?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Tomer Brisker/>
            <br />
            <sub style="font-size:12px"><b>Tomer Brisker</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/donv>
            <img src=https://avatars.githubusercontent.com/u/57275?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Uwe Kubosch/>
            <br />
            <sub style="font-size:12px"><b>Uwe Kubosch</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/valera-rozuvan>
            <img src=https://avatars.githubusercontent.com/u/2273090?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Valera Rozuvan/>
            <br />
            <sub style="font-size:12px"><b>Valera Rozuvan</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/voxik>
            <img src=https://avatars.githubusercontent.com/u/14406?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Vít Ondruch/>
            <br />
            <sub style="font-size:12px"><b>Vít Ondruch</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/MingStar>
            <img src=https://avatars.githubusercontent.com/u/412455?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Weiming Chen/>
            <br />
            <sub style="font-size:12px"><b>Weiming Chen</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/igrep>
            <img src=https://avatars.githubusercontent.com/u/227057?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=YAMAMOTO Yuji/>
            <br />
            <sub style="font-size:12px"><b>YAMAMOTO Yuji</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/kurotaky>
            <img src=https://avatars.githubusercontent.com/u/866589?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Yuta Kurotaki/>
            <br />
            <sub style="font-size:12px"><b>Yuta Kurotaki</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/benilovj>
            <img src=https://avatars.githubusercontent.com/u/23801?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Jake Benilov/>
            <br />
            <sub style="font-size:12px"><b>Jake Benilov</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/chocolateboy>
            <img src=https://avatars.githubusercontent.com/u/31533?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=chocolateboy/>
            <br />
            <sub style="font-size:12px"><b>chocolateboy</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/chrisk>
            <img src=https://avatars.githubusercontent.com/u/1426?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Chris Kampmeier/>
            <br />
            <sub style="font-size:12px"><b>Chris Kampmeier</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/evverx>
            <img src=https://avatars.githubusercontent.com/u/10195800?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Evgeny Vereshchagin/>
            <br />
            <sub style="font-size:12px"><b>Evgeny Vereshchagin</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/ReadmeCritic>
            <img src=https://avatars.githubusercontent.com/u/15367484?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=ReadmeCritic/>
            <br />
            <sub style="font-size:12px"><b>ReadmeCritic</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/grosser>
            <img src=https://avatars.githubusercontent.com/u/11367?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Michael Grosser/>
            <br />
            <sub style="font-size:12px"><b>Michael Grosser</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/hakeda>
            <img src=https://avatars.githubusercontent.com/u/10025340?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=hakeda/>
            <br />
            <sub style="font-size:12px"><b>hakeda</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/jeanlange>
            <img src=https://avatars.githubusercontent.com/u/1461735?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Jean Lange/>
            <br />
            <sub style="font-size:12px"><b>Jean Lange</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/jcs>
            <img src=https://avatars.githubusercontent.com/u/9888?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=joshua stein/>
            <br />
            <sub style="font-size:12px"><b>joshua stein</b></sub>
        </a>
    </td>
</tr>
<tr>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/ptarjan>
            <img src=https://avatars.githubusercontent.com/u/40143?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Paul Tarjan/>
            <br />
            <sub style="font-size:12px"><b>Paul Tarjan</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/rudyyazdi>
            <img src=https://avatars.githubusercontent.com/u/12105389?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Rudy/>
            <br />
            <sub style="font-size:12px"><b>Rudy</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/shunsuke227ono>
            <img src=https://avatars.githubusercontent.com/u/7357864?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=大野峻典/>
            <br />
            <sub style="font-size:12px"><b>大野峻典</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 75.0; height: 75.0">
        <a href=https://github.com/windwiny>
            <img src=https://avatars.githubusercontent.com/u/45995?v=4 width="50;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=windwiny/>
            <br />
            <sub style="font-size:12px"><b>windwiny</b></sub>
        </a>
    </td>
</tr>
</table>
