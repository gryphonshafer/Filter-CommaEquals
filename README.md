# NAME

Filter::CommaEquals - Adds support for ,= to any package or script

# VERSION

version 1.02

[![test](https://github.com/gryphonshafer/Filter-CommaEquals/workflows/test/badge.svg)](https://github.com/gryphonshafer/Filter-CommaEquals/actions?query=workflow%3Atest)
[![codecov](https://codecov.io/gh/gryphonshafer/Filter-CommaEquals/graph/badge.svg)](https://codecov.io/gh/gryphonshafer/Filter-CommaEquals)

# SYNOPSIS

    use Filter::CommaEquals;
    my @array = ( 42, 1138, 96 );

    @array ,= 433;
    # exactly the same as writing: push( @array, 433 );

    print join(', ', @array), "\n";
    # prints: 42, 1138, 96, 433

# DESCRIPTION

Adds support for ,= to any package or script. Perl has +=, -=, /=, \*=, .=, and
so forth to operate on scalars, but it doesn't have ,= to operate on arrays.
This module effectively lets you rewrite push statements with ,= instead.

For example...

    push @array, $element;
    push( @array, $element_1, $element_2, $element_3 );
    push @array, [ 42, 1138, 96, 433 ];

...can now be rewritten as...

    use Filter::CommaEquals;
    @array ,= $element;
    @array ,= $element_1, $element_2, $element_3;
    @array ,= [ 42, 1138, 96, 433 ];

Cool, huh? Admit it. You want to write ,= instead of push, don't you.
You can save typing 3 whole characters!

Filter::CommaEquals is scoped to the package or script that it's used in,
but nothing more, and it requires Perl version 5.7.1 or higher.

# MOTIVATION

A coworker complained about ,= not being in core Perl. After some thought,
I realized writing ,= is faster (by 3 key presses) than push. Also, I'm lazy.

# SEE ALSO

You can also look for additional information at:

- [GitHub](https://github.com/gryphonshafer/Filter-CommaEquals)
- [MetaCPAN](https://metacpan.org/pod/Filter::CommaEquals)
- [GitHub Actions](https://github.com/gryphonshafer/Filter-CommaEquals/actions)
- [Codecov](https://codecov.io/gh/gryphonshafer/Filter-CommaEquals)
- [CPANTS](http://cpants.cpanauthors.org/dist/Filter-CommaEquals)
- [CPAN Testers](http://www.cpantesters.org/distro/F/Filter-CommaEquals.html)

# AUTHOR

Gryphon Shafer <gryphon@cpan.org>

# COPYRIGHT AND LICENSE

This software is copyright (c) 2021 by Gryphon Shafer.

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.
